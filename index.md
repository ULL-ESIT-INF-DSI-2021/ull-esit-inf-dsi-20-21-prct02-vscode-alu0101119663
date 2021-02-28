# Práctica 2 - Instalación y configuración de Visual Studio Code

## Introducción

Durante esta práctica se llevará a cabo la instalación y configuración del entorno Visual Studio Code, el cual usaremos durante todo el desarrollo de la asignatura. **Visual Studio Code** (VSC) es un editor de código fuente. Incluye soporte para realizar depuración de código, control integrado de **Git**, resaltado de sintaxis, finalización inteligente de código, fragmentos y refactorización de código.

## Objetivos de la práctica

- Configurar el entorno de **VSC** para realizar las prácticas de la asignatura.
- Aprender a configurar y trabajar con diferentes extensiones que nos ofrece el entorno.
- Realización del primer proyecto en **TypeScript**.

## Instalación del Visual Studio Code

Para empezar a familiarizarnos con este programa, como es lógico, debemos instalarlo en caso de que ya no lo tengamos hecho. Existen dos opciones, hacerlo con *apt* o mediante *snap*. La primera la haremos mediante *apt*:

```
jaco@jaco-N551JK:~$ sudo apt install code
```

Para instalar el entorno de desarrollo mediante la *Snap Store*, se hace de la siguiente manera: 

```
jaco@jaco-N551JK:~$ sudo snap install code --classic
```

Poniendo el argumento *--classic* haremos que se instale sin las funciones de banco de pruebas estrictas que normalmente se usan en las Snaps. Este argumento es importante ya que se necesita un acceso privilegiado al sistema para empaquetar las aplicaciones de una forma fiable.

## Configuración del Visual Studio Code

### Configuración para conectarse a una máquina virtual remota mediante Visual Studio Code
Para realizar esta conexión debemos asegurarnos de que estamos bajo la red de la Universidad de La Laguna, o que en su defecto, estamos conectados en la VPN a la misma. Como primer paso debemos asegurarnos de que tenemos la extensión **Remote - SSH** instalada. En caso de que no sea así debemos instalarla.
Para instalar la extensión debemos ir al panel izquierdo de Visual Studio Code y hacer clic en el apartado de *Extensions*, una vez ahí, en el buscador tecleamos **Remote - SSH** y le damos a *Install*. En caso de duda puede encontrar mas información en el siguiente enlace:  [Instalar extensiones].(https://code.visualstudio.com/docs/editor/extension-gallery)

Una vez que se haya completado la instalación, pulsamos la tecla *F1* y escribimos *ssh*, pulsamos sobre *Connect to Host*, y si se completó la práctica 1 de la forma en que se indicaba nos saldrá el nombre de la máquina virtual en el menú desplegable. En caso de que no sea así, probablemente habría que revisar la configuración del fichero *~/.ssh/config*. 

Como podemos apreciar, en nuestro caso tenemos la configuración correcta.

```
Host iaas-dsi55
  HostName iaas-dsi55
  User usuario
 ```

En caso de que ocurra este error, la recomendación es que vuelva a repasar la [Práctica 1: Configuración de máquina virtual en el IaaS](https://ull-esit-inf-dsi-2021.github.io/ull-esit-inf-dsi-20-21-prct01-iaas-alu0101119663/).

Una vez hagamos clic sobre el nombre de la máquina deseada, se nos abrirá una nueva ventana de VSC. Comprobaremos que estemos en la máquina virtual que queremos, abriendo la terminal integrada con el siguiente comando:

```
[~()]$hostname
iaas-dsi55
```

### Sesiones colaborativas con Visual Studio Live Share
Visual Studio Live Share permite que varias personas puedan colaborar en un proyecto que tengan en común en tiempo real. Para poder utilizar esta función que nos ofrece Visual Studio Code, debemos instalar una extensión llamada [Live Share Extension Pack](https://marketplace.visualstudio.com/items?itemName=MS-vsliveshare.vsliveshare-pack) así como todas las que se nos recomienda en el manual anterior. 

Para instalar las extensiones debemos recordar en qué máquina estamos y donde queremos instalarla, ya que si la instalamos en la máquina virtual no estarán en la local, y para instalarla debemos salir de la conexión mediante SSH,y quedarnos con la ventana del Visual Studio Code de la máquina local.

Una vez instalada, podemos abrir un proyecto para editar nosotros solos, o pinchar sobre el botón con forma de flecha en el lateral izquierdo, y nos ofrecerá crear una sesión colaborativa o unirnos a una ya creada. Con esta extensión podremos realizar sesiones colaborativas como se ha dicho, además de otras funcionalidades como chats, llamadas o pizarra.

Una vez hayamos iniciado sesión en el lateral izquierdo nos aparecerá la siguiente información:

```
ᐯ SESSION DETAILS
  ᐯ Participants (0)
     Invite particpants...
  ᐯ Shares Servers (0)
     Share server...
  ᐯ Shared Terminals (0)
     Share terminal...
    Comments (0)
  ᐯ Audio Call (0)
     Start audio call...
ᐯ CONTACTS
  ᐯ Recent contacts (0)
     Invite particpants...
  ᐯ Sugested contacts (0)
     null...
```


























