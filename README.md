# Como Crackear StarUML
## 1º Descarga StarUML:
[StarUML Download](https://staruml.io/download)

## 2º Descargar NodeJs:
[NodeJs Download](https://nodejs.org/en/download/)

## 3º Instalar Asar:
Abres un terminal e introduces este codigo:

``
nmp install asar -g
``

## 4º Una vez instalado StarUML:
Seleccionamos el icono del escritorio con click derecho y le damos a: **_Abrir la ubicación del archivo_**
Si no hemos cambiado la ruta de instalación antes deberia ser esta: 

``
C:\Program Files\StarUML
``

Si es asi abrimos una terminal en modo administrador y ejecutamos los siguientes codigos:

``
cd C:\Program Files\StarUML\resources asar extraxt app.asar app
``

Este codigo descomprimira el archivo **_app.asar_** en una carpeta en el mismo repositorio que se llamara app no cierres el terminal todavia dejalo en 2º plano.
Una vez la descomprima entramos en la carpeta generada por npm llamada **_App_** y seguimos esta ruta:

``
C:\Program Files\StarUML\resources\app\src\engine
``

En esta carpeta abrimos el archivo: **_license-manager.js_** con cualquier editor de codigo que admita JavaScript
Y buscamos la función **_checkListValidity ()_**, y cambiamos el status de false a true, y el registerLog lo ponemos como comentario, asi quedaria:

```JavaScript
checkLicenseValidity () {
    if (packageJSON.config.setappBuild) {
      setStatus(this, true)
    } else {
      this.validate().then(() => {
        setStatus(this, true)
      }, () => {
        //setStatus(this, false)
        //UnregisteredDialog.showDialog()
        setStatus(this, true)
      })
    }
  }
```

Una vez modificado guardamos el archivo y pasamos a otro archivo.
Ahora desactivaremos las actualizaciones, en la misma carpeta abrimos el archivo: **_update_manager.js_**
Buscamos la funcion: **_handleMessages ()_**, y ponemos como comentario todas las lineas: **_"this."_**, y asi quedaria:

```JavaScript
handleMessages () {
    ipcRenderer.on('autoUpdater:update-available', (event, info) => {
      //this.state = 'available'
      //this.updateInfo = info
      //this.emit('update-available', info)
    })
    ipcRenderer.on('autoUpdater:update-not-available', (event, info) => {
      //this.state = 'no-update'
      //this.updateInfo = info
      //this.emit('update-not-available', info)
    })
    ipcRenderer.on('autoUpdater:download-progress', (event, progress) => {
      //this.state = 'downloading'
      //this.progress = progress
      //this.emit('download-progress', progress)
    })
    ipcRenderer.on('autoUpdater:update-downloaded', (event, info) => {
      //this.state = 'ready'
      //this.updateInfo = info
      //this.emit('update-downloaded', info)
    })
    ipcRenderer.on('autoUpdater:error', (event, err) => {
      this.emit('update-error', err)
    })
  }
```

Una vez modificados y guardados los archivos,le cambiamos el nombre por ejemplo:**_"appOld.asar"_** o eliminamos el archivo original: **_app.asar_** y nos pasamos al terminal que teniamos abierto y ejecutamos el comando:

``
asar pack app app.asar
``

Una vez comprimido ya tendremos StarUML activado y con las actualzaciones bloqueadas.

## Si quieres descargar directamente el app.asar para StarUML v5.0.2:
[Google Drive Download](https://drive.google.com/file/d/1Z_6YEJxiSgt0pakb40Gi25FgHPnrJBOg/view?usp=sharing)

[MEGA Download](https://mega.nz/file/FT1Q3aiI#BeKiBDEsiN0R2wBNeHSFCOs8LLKiYMEAHnJZhGP2diI)

[MediaFire Download](https://www.mediafire.com/file/xm0oq9zve64l4sj/app.asar/file)

[anonfiles Download](https://anonfiles.com/79A977E9y4/app_asar)

