# How to Crack StarUML
# 1º Descarga StarUML:
[StarUML Download](https://staruml.io/download)

# 2º Descargar NodeJs:
[NodeJs Download](https://nodejs.org/en/download/)

# 3º Instalar Asar:
Abres un terminal e introduces este codigo:

``
nmp install asar -g
``

# 4º Una vez instalado StarUML:
Seleccionamos el icono del escritorio con click derecho y le damos a: **_Abrir la ubicación del archivo_**
Si no hemos cambiado la ruta de instalación antes deberia ser esta: 

``
C:\Program Files\StarUML
``

Si es asi abrimos una terminal en modo administrador y ejecutamos los siguientes codigos:

``
cd C:\Program Files\StarUML\resources asar extraxt app.asar app
``

Este codigo descomprimira el archivo **app.asar** en una carpeta en el mismo repositorio que se llamara app.
Una vez la descomprima entramos en la carpeta generada por npm llamada **App** y seguimos esta ruta:

``
C:\Program Files\StarUML\resources\app\src\engine\
``

