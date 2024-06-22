+++
title = 'Lo que nosotros construimos y lo que watchtower destruyó'
description = 'Jorge e Ibai se adentran a la aventura de... Docker'
date = 2023-04-28T00:00:00+02:00
draft = false
tags = ['docker']
+++

Todo empezó porque un amigo de la uni y yo decidimos comprar (¿alquilar?) una VPS de [contabo](https://url.intron014.com/rvwbH), en específico la [VPS S](https://url.intron014.com/gPAwZ) ya que no necesitamos **tanta** potencia (o eso pensábamos).

Decidimos usar una combinación de Docker y Portainer (Business Edition, por supuesto) ya que Proxmox es demasiado para lo que teníamos en mente. Y así, los contenedores fueron apareciendo, comenzando por [Homepage](https://github.com/benphelps/homepage) y [Homer](https://github.com/bastienwirtz/homer) para tener algún lugar para acceder a los servicios rápidamente, después vino, tras muchas horas investigando opciones, [Uptime Kuma](https://github.com/louislam/uptime-kuma), un maravilloso sistema para monitorizar nuestros contenedores y poder arreglarlo lo antes posible (y sinceramente, lo hace bastante simple con su integración de WebHooks de Discord y bots de Telegram). [Aquí](https://status.intron014.com) está el resultado final.

En fin, y así continuamos con un acortador de enlaces, [Shlink](https://github.com/shlinkio/shlink) y demás, hasta que nos topamos con un pequeño problema... Los contenedores no se actualizan solos, y teniendo en cuenta que pasamos de un par de contenedores a tener más de veinte en menos de dos semanas, esto se podía comenzar a complicar... Por suerte (o no tanta), encontramos [Watchtower](https://github.com/containrrr/watchtower), una herramienta que, cuando está configurada correctamente, es super poderosa, actualizando los contenedores que lo requieran en la hora que quieras (No como otros... Windows, te estoy mirando a ti). Todo genial, ¿no?. Pues no. 

Pasaron los días, y las actualizaciones vinieron y fueron hasta que... **BAM**, alertas de Uptime Kuma por todos lados. ¡Umami se ha caido! - Me dijo Ibai, mi compañero de servidor) - ¡Grafana no va! - Dije yo - Y así continuamente hasta que la avalancha de contenedores acabó... ¿Que qué ha pasado os preguntais?, nosotros también, pero teníamos un claro culpable... Watchtower.

Debido a que tampoco éramos expertos en Docker ni Docker Compose, algunos volúmenes no estaban bien montados provocando la pérdida de unas cuantas horas de configuración, algunas etiquetas de versión estaban fijas (patata:69.54), haciendo que los contenedores que dependían de ello, al actualizarse, dejaran de soportar esa versión... En fin, un disaster total, pero mejor con 30 contenedores que teniendo un servidor con 500... En el fondo, ese va a ser mi trabajo cuando salga de la carrera.

Pero vamos, que de esto se puede sacar una buena lección... *aprender a usar bien Docker Compose y configurar bien los contenedores* :)