---
layout: post
title: ¿Cómo instalar y configurar rclone en Manjaro?
---

¡Buenas! el día de hoy te vamos a explicar cómo instalar **rclone** en Manjaro Linux.

**rclone** es una aplicación libre para sincronizar nuestros archivos con una amplia variedad de servicios en la nube

## 1) Instalación

Como primer paso, vamos a instalar *rclone* en nuestra PC, para eso **abrimos la terminal** y ejecutamos

``` bash
sudo pacman -S rclone
```

Luego nos solicitará una confirmación que haremos ingresando "y" o "s" según corresponda

![Instalación de rclone 1]({{ site.baseurl }}/images/2020-09-07-instalar-rclone-en-manjaro/photo_2020-09-07_19-06-13.jpg)

![Instalación de rclone 2]({{ site.baseurl }}/images/2020-09-07-instalar-rclone-en-manjaro/photo_2020-09-07_19-06-14.jpg)

Al terminar la ejecución, tendremos ***rclone*** instalado en una PC

## 2) Configuración

Llega el momento de conectar la aplicación con nuestro(s) hosting(s) en la nube, para iniciar el proceso, ingresamos en consola el siguiente comando

``` bash
rclone config
```

![Instalación de rclone 3]({{ site.baseurl }}/images/2020-09-07-instalar-rclone-en-manjaro/photo_2020-09-07_19-06-15.jpg)

Ingresamos "n" indicando que vamos a agregar una nueva conexión remota, y luego aparecerá el listado de servicios a los que nos podemos conectar, en este caso, vamos a conectarnos a OneDrive mediante una cuenta de Office365, que en este caso es el 23, pero puede variar según la versión o distribución que estemos usando

![Instalación de rclone 4]({{ site.baseurl }}/images/2020-09-07-instalar-rclone-en-manjaro/photo_2020-09-07_19-06-16.jpg)

A partir de ahora la configuración puede variar según el servicio, pero para el caso de OneDrive, debemos hacer lo siguiente:

Cuando nos solicite "client_id" y "client_secret"


The easiest way to make your first post is to edit this one. Go into /_posts/ and update the Hello World markdown file. For more instructions head over to the [Jekyll Now repository](https://github.com/barryclark/jekyll-now) on GitHub.
