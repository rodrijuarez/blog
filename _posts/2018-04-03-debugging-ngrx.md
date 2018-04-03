---
layout: post
title: Debuggeando ngrx tests
---

Me encontré con varios problemas al querer debuggear una aplicación en la que
tengo ngrx y karma, ya que no había manera de ver las acciones que eran
disparadas por mi aplicación ni forma de ver el state adentro de mis tests de
integración. Por lo tanto acá dejo un mini resumen de las cosas que fui
configurando para sacar esto andando.

Primero que todo no se olviden de importar en su TestBed el modulo
StoreDevtools, esto basicamente ya lo tienen en su main module. Basicamente esto
los habilita a usar esta
[extension para Chrome](https://chrome.google.com/webstore/detail/redux-devtools/lmhkpmbekcpmknklioeibfkpmmfibljd)
(también disponible para Firefox)

```
import { StoreDevtoolsModule } from '@ngrx/store-devtools';

    ...

    StoreDevtoolsModule.instrument({
        maxAge: 25 // Config que quieran y manejen ustedes para debuggear en las dev tools
    })

    ...
```

Después de eso por comodidad en Karma pueden agregar su propio browser con
configuración personalizada:

```
   browsers: [...otrosBrowser, 'ChromeWithDebugging'],
   customLaunchers: {
   	ChromeWithDebugging: {
	    base: 'Chrome',
 	    chromeDataDir: path.resolve(__dirname, '.chrome')
       }
   }
```

En este caso lo único que agrego es un directorio dedicado para mi browser
personalizado, custión de poder instalar extensiones para Chrome y no tener que
reinstalar cada vez que corro los tests, en este caso la única extensión sería
la extensión de Redux

En la section de scripts del `package.json` lo que quedaría hacer sería usar el browser custom:

```
    "test-watch": "ng test --browsers ChromeWithDebugging",
```

No se olviden tampoco de agregar en el `.gitignore` la carpeta donde van a tirar la data del browser custom que agregaron:

``` 
.chrome
```
