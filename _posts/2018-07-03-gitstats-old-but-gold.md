---
layout: post
title: Gitstats - Old but gold
---
<img src="https://hipertextual.com/files/2016/01/the_big_short_adam_mckay-1000x563.jpg"/>

  El otro día estaba pensando en si había una métrica o algún tipo de insight que nos pudiera decir si un equipo se está volviendo más o menos productivo y al mismo tiempo compararlo con la cantidad de líneas de código a través del tiempo, y me encontré con el bendito [GitStats](http://gitstats.sourceforge.net/).

  Lo bueno de está tool es que podes la cantidad de commits que se tiene en un repo por semana o mes para ver si hay alguna especie de trend y lo mismo con las líneas de código, aclaro que porque alguien escriba más líneas de código no significa que sea más productivo o no, pero mirando esto sobre todo un equipo y analizando la tendencia podes llegar a tener una noción de problemas que pueden aparecer en el futuro o confirmar lo temido :).

  Por dar un ejemplo, digamos que las líneas del proyecto donde trabajas venían aumentando tremendamente y la cantidad de commits en los últimos meses era un average de 100, pero desde hace 3 meses el average bajó gradualmente a 70 y las líneas de código no aumentan “tan rápido”, si simplemente un dev se bajó del team parecería lógico, pero qué pasa si simplemente tu proyecto se está volviendo inmantenible poco a poco sin que te dieras cuenta?

  Bueno, ahora a correr gitstats y a pedir esos refactor
