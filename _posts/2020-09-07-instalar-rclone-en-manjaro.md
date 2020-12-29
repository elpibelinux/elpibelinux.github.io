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

Ingresamos "n" indicando que vamos a agregar una nueva conexión remota, indicamos un nombre para esta conexión y luego aparecerá el listado de servicios a los que nos podemos conectar.

### 2.1) Microsoft OneDrive Office3655

En este caso, vamos a conectarnos a OneDrive mediante una cuenta de Office365, que en este caso es el 23, pero puede variar según la versión o distribución que estemos usando

![Instalación de rclone 4]({{ site.baseurl }}/images/2020-09-07-instalar-rclone-en-manjaro/photo_2020-09-07_19-06-16.jpg)

A partir de ahora la configuración puede variar según el servicio, pero para el caso de OneDrive, debemos hacer lo siguiente:

Cuando nos solicite "client_id" y "client_secret" no ingresamos nada y le damos Enter, lo mismo cuando nos solicite "Edit advanced config?" (por defecto no) y "Use auto config?" (por defecto si) ya que estamos configurando una cuenta simple. A continuación se abrirá un navegador que nos solicitará nuestras credenciales de Office365.

![Instalación de rclone 5]({{ site.baseurl }}/images/2020-09-07-instalar-rclone-en-manjaro/photo_2020-09-07_19-06-17.jpg)

Al finalizar, nos consultará que tipo de cuenta vamos a configurar, en nuestro caso marcamos la "1" (OneDrive Personal or Business).

![Instalación de rclone 6]({{ site.baseurl }}/images/2020-09-07-instalar-rclone-en-manjaro/photo_2020-09-07_19-06-18.jpg)

Luego nos solicitará el disco de OneDrive, que normalmente será "0"; chequeamos la información y ponemos "y", a continuación, salimos con "q".

Después abrimos la configuración de startup (inicio) y añadimos la siguiente línea para que monte la carpeta sincronizada en el inicio de nuestra pc

``` bash
sh - c "rclone --vfs-cache-mode writes mount [nombre]: [dirección]"
```

Donde "nombre" es el nombre que le asignamos a la conexión cuando iniciamos el "rclone config" y "dirección" es la carpeta donde se van a sincronizar los archivos. Por ejemplo podría quedar algo así:

``` bash
sh - c "rclone --vfs-cache-mode writes mount MiNube: /home/elpibelinux/OneDrive"
```

![Instalación de rclone 7]({{ site.baseurl }}/images/2020-09-07-instalar-rclone-en-manjaro/photo_2020-09-07_19-06-21.jpg)

![Instalación de rclone 8]({{ site.baseurl }}/images/2020-09-07-instalar-rclone-en-manjaro/photo_2020-09-07_19-06-24.jpg)

## 3) Finalización

¡Y Listo! Ahora solo toca reiniciar la PC y ya estaremos sincronizando nustro servicio en la nube con una carpeta local.


## Agradecimientos

A [Martín Guzmán](https://twitter.com/Martinn01) por las imágenes e instrucciones para este tutorial.

[Sitio oficial rclone](https://rclone.org/)
