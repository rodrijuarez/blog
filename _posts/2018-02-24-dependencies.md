---
layout: post
title: No te olvides de tus dependencies
---
<img src="https://jamesfoleyillustrations.files.wordpress.com/2016/03/12-monkeys-dutch-tilt.jpg?w=840&h=460"/>
 El otro día se nos dió por mirar las dependencies que teníamos en nuestro proyecto y cuanto pesaba cada una, para esto usamos webpack-bundle-analyzer, tiene una UI bastante fea cuando te devuelve los results pero bueno, cumple su cometido.

 No muy asombrados nos damos cuenta que nuestro proyecto tiene bastante basura y cosas que no usamos, por ej se importa toda la librería de rxjs y lodash, en vez de usar las funciones y operators que necesitamos (ej: `import omit from 'lodash/omit'` => usen esto :), o esto `const omit = require('lodash/omit')` ). Así que ahora hay que ir switcheando de a poco estás cosas habiendo más de 300 lugares en los que usamos lodash y ni hablar de rxjs... Como recomendación checkeen cómo tienen que importar las cosas para no traerse toda la librería al bundle que generan y vean cuánto agrega esa librería que están agregando al bundle de su proyecto. El segundo problema lo estamos teniendo también con los types de lodash que si lo importas de otra manera no tenes los typings :( and that makes us sad. But first things first, primero hay que reemplazar todos los imports viejos de lodash por lo nuevo y luego veremos... de la nueva manera es mucho mas facil de reemplazar con un comando en bash o un script

 Por otro lado tenemos moment y moment-timezone que son ambos algo bastante standard para el manejo de fechas y por default te traen todos los locales y un monton de basura cuando los importas, por ahora para esto encontre la alternativa de date-fns. Por suerte no somos tan dependientes de moment como de las otras librerías, así que el switch es bastante más fácil y no necesita ser tan progresivo.

 tldr: fijense el size del bundle cada vez que agregan algo, y no importen toda la libreria, seria una lastima que tu bundle termine pesando 1mb :/
