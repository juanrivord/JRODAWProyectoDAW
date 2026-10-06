# Guía de creacion de un proyecto, enlace SFTP con el servidor y enlace con GitHub



#### Datos adicionales
Estamos utilizando Windows 10 como sistema operativo cliente, guardando los proyectos en:

D:\Datos\Proyectos\

Utilizando Google Chrome como navegador de pruebas y uso.

---

> [!NOTE]
> En este caso vamos a utilizar Visual Studio Code como IDE, explicare tanto la creación como, configuración, conexion SFTP, conexión Github y borrado del proyecto desde Visual Studio Code.

## Fase 0. Instalación de extensiones

En la parte izquierda en el icono ![IconoExtension](images/iconoExtensiones.PNG) o pulsando la combinacion de teclas (Crtl+Shift+X) abrimos la ventana de extensiones, buscaremos instalar esta lista:

* SFTP
* Live Server
* Path Intellisense _(Opcional)_ **Recomendado**
* PHP
* PHP Profiler 
* HTML CSS Support
* HTML/CSS/JavaScript Snippets _(Opcional)_ **Recomendado**
* Auto Rename Tags _(Opcional)_ **Recomendado**
* Remote - SSH _(Opcional)_ **Recomendado**

Le daremos click a instalar y si nos pide algun tipo de confirmación, aceptaremos **Trust Publishers** y siguiente.


## Fase 1. Creación del proyecto

### Creamos la carpeta en la que vamos a guardar nuestro proyecto inicialmente.


Arriba a la izquierda pulsamos:

- File\Open Folder
  
Y cuando nos de a elegir una carpeta, seleccionamos la carpeta nueva de nuestro proyecto, o simplemente la creamos y la utilizamos.

Nos tiene que quedar algo asi:

![ProyectoNuevoCreado](images/proyectoNuevoCreado.PNG)

### Creamos estructura básica para trabajar

Un archivo nuevo que se llame **index.html** pulsando en el icono del archivo New File...

![indiceProyectoNuevo](images/index.PNG)

Colocaremos una estructura básica de html:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
    
</body>
</html>
```

---

### Vamos a meter en este proyecto los archivos del Tema 3

Movemos todos los archivos del tema 3 dentro del proyecto, sin cambiar nada
![ImagenProyectoTema3](images/proyectoTema3Clonado.PNG)

## Fase 2. Enlace SFTP con el servidor

Utilizando la extention **SFTP** vamos a conectarnos al servidor, pulsamos **F1** y abrimos la paleta de comandos. Pulsamos en **SFTP: Config**.
![sftpConfig](images/sftpconfig.PNG)

Se nos abrira un **JSON** con información sobre la configuracion SFTP. Colocaremos la siguiente configuración:

```json
{
    "name": "My Server",
    "host": "10.199.8.97", # Aqui ponemos la ip de nuestra máquina
    "protocol": "sftp",
    "port": 22,
    "username": "operadorweb", # El usuario configurado
    "password": "paso", # Su contraseña
    "remotePath": "/var/www/html/DWESProyecto4/", # El directorio que queremos usar
    "uploadOnSave": true, # Con esto pasa los archivos cada vez que guarda
    "useTempFile": false,
    "openSsh": false,
    "ignore": [
        "**/.git/**",
        "**/.vscode/**",
        "**/node_modules/**"
    ]
}
```