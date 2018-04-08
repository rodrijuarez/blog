---
layout: post
title: Pequeño recordatorio sobre Ramda y Typescript
---

Estos últimas semanas estuve trabajando con Ramda y TypeScript en un proyecto y
cuando agregué al principio la librería de tipos de Ramda, agregué
equivocadamente

```
@types/ramda
```

A modo de recordatorio/aviso, agreguen
[esta](https://github.com/types/npm-ramda):

```
types/npm-ramda#dist
```

Está librería está actualizada con la última versión de Ramda además de que
tiene mejores tipados, aparentemente
[están trabajando](https://github.com/types/npm-ramda/issues/191) para que este
repositorio pueda ser compatible de nuevo con
[DefinetelyTyped](https://github.com/DefinitelyTyped/DefinitelyTyped) que es el
normalmente usado para los tipados de librerias externas en TypeScript
