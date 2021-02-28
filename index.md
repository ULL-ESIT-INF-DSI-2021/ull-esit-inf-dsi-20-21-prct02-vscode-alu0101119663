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
**Visual Studio Live Share** permite que varias personas puedan colaborar en un proyecto que tengan en común en tiempo real. Para poder utilizar esta función que nos ofrece Visual Studio Code, debemos instalar una extensión llamada [Live Share Extension Pack](https://marketplace.visualstudio.com/items?itemName=MS-vsliveshare.vsliveshare-pack) así como todas las que se nos recomienda en el manual anterior. 

Para instalar las extensiones debemos recordar en qué máquina estamos y donde queremos instalarla, ya que si la instalamos en la máquina virtual no estarán en la local, y para instalarla debemos salir de la conexión mediante **SSH**,y quedarnos con la ventana del Visual Studio Code de la máquina local.

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

## Primer proyecto en TypeScript

Antes de empezar con nuestro proyecto debemos instalar la extension *ESLint*, la cual nos permitirá realizar comprobaciones sobre el estilo de nuestros ficheros que incluyen el código fuente en **JavaScript** y **TypeScript**. Para su instalación repetiremos lo mismo que con las extensiones anteriores, iremos al panel izquierdo, haremos clic sobre el botón de *Extensions* y en el buscador pondremos *ESLint* y pulsaremos finalmente sobre *Install*, una vez finalizado ya estaría lista para ser usada. Además si estamos habituados a usar *Vim* podremos instalar esta extensión de la misma manera.

Ahora instalaremos el compilador de TypeScript usando **NPM** (Node Package Manager) en nuestra máquina virtual. Para ello abriremos una terminal en Visual Studio Code, para ello hay dos formas, la primera es ir al menú superior, hacer clic sobre *Terminal* -> *New Terminal* o la otra forma es con la combinación de teclas *[Ctrl + Shift + ']*. Una vez abierta introducimos el siguiente comando: 

```
[~()]$npm install --global typescript

added 1 package, and audited 2 packages in 4s

found 0 vulnerabilities

[~()]$tsc --version
Version 4.2.2
```
Al poner el argumento *--global* hacemos que el paquete que se va a instalar, lo haga de manera global.

Una vez llegado hasta aquí ya habremos instalado el compilador **TypeScript**. El siguiente paso es crear el directorio de trabajo para nuestro proyecto, para ello realizaremos los siguiente comandos para crearlo en la ruta */home/usuario*. Una vez allí con un *npm init --yes* haremos que se inicialice nuestro proyecto creando el fichero *package.json* que establecerá las dependencias para el desarrollo y ejecución de nuestro proyecto.

```
[~()]$pwd
/home/usuario
[~()]$mkdir hello-world
[~()]$cd hello-world/
[~/hello-world()]$npm init --yes
Wrote to /home/usuario/hello-world/package.json:

{
  "name": "hello-world",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "echo \"Error: no test specified\" && exit 1"
  },
  "keywords": [],
  "author": "",
  "license": "ISC"
}

[~/hello-world()]$ls -lrtha
total 12K
drwxr-xr-x 11 usuario usuario 4,0K feb 24 10:11 ..
-rw-rw-r--  1 usuario usuario  225 feb 24 10:12 package.json
drwxrwxr-x  2 usuario usuario 4,0K feb 24 10:12 .
```
Una vez creado vamos a hacer que el **VSC** muestre el directorio, para ello en el menú superior, hacemos clic en *File* -> *Open Folder* y elegimos el directorio deseado, en nuestro caso *hello-world*.

Tambien se podrá añadir a un *workspace* (espacio de trabajo). Para ello volvemos a ir al apartado de *File* y seleccionaremos esta vez *Add Folder to Workspace*. Seleccionamos nuestra carpeta *hello-world*. Si no teníamos un *workspace* crearemos uno. Guardamos el espacio de trabajo con la opcion de *Save Workspace As* del apartado *File*, escribimos el respectivo nombre y pulsamos *Ok*.

El siguiente paso es que creemos un nuevo fichero en nuestro directorio ```hello-world``` denominado ```tsconfig.json```. En este fichero se especifican las opciones del compilador de **TypeScript**.

 ```
 [~/hello-world()]$touch tsconfig.json
[~/hello-world()]$vi tsconfig.json 
[~/hello-world()]$cat tsconfig.json 
{
        "compilerOptions": {
                "target": "ES2018",
                "outDir": "./dist",
                "rootDir": "./src",
                "module": "CommonJS"
        }
}
```

Estas opciones que hemos añadido al fichero ```tsconfig.json``` le indican al compilador de **TypeScript** que primero queremos que genere un código que sea compatible con los últimos estándares de **JavaScript**. El código **JavaScript** producto de la compilación se almacenará en un directorio llamado ```dist```. El código fuente en **TypeScript* se almacenará en el directorio ```src```. Por último, se indica un estándar para cargar código desde ficheros independientes.

Ahora crearemos un fichero para el codigo **TypeScript** de la siguiente manera: 

```
[~/hello-world()]$pwd
/home/usuario/hello-world
[~/hello-world()]$mkdir src
[~/hello-world()]$cd src
[~/hello-world/src()]$touch index.ts
[~/hello-world/src()]$ls
index.ts
```
Vamos a añadir una simples lineas al código, en este caso un *"Hola Mundo"*.

```
[~/hello-world/src()]$vi index.ts 
[~/hello-world/src()]$cat index.ts 
let myString: string = "Hola Mundo";
console.log(myString);
```
Para compilar el código escrito antes, usamos el siguiente comando:

```
[~/hello-world/src()]$tsc
```

Esto ha creado el directorio *dist*, ademas se creo un fichero ```index.js```. Como podemos ver tenemos dos **index.js** en diferentes carpetas, vamos a ver si el contenido de los archivos es igual.

```
[~/hello-world/src()]$cat index.ts 
let myString: string = "Hola Mundo";
console.log(myString);

[~/hello-world/src()]$cat ../dist/index.js 
let myString = "Hola Mundo";
console.log(myString);
```

Como se puede apreciar claramente, la diferencia reside en la declaracion de la variable **myString**, esto ocurre ya que como bien sabemos, **TypeScript** si utiliza tipos para tratar de evitar los problemas que surgen con **JavaScript**, ya que este ultimo no es un lenguaje tipado.

Para ejecutar el código de **JavaScript** generado a partir del código **TypeScript** se hace mediante el comando:

```
[~/hello-world()]$node dist/index.js 
Hola Mundo
```

## Conclusiones
La realización de esta práctica me ha resultado que no tenía un gran nivel de dificultad debido a que he ido usando Visual Studio Code y muchas de sus extensiones durante todo el transcurso de la carrera. Sin embargo, me ha parecido realmente útil la extensión para realizar sesiones colaborativas ya que desconocía la existencias de ellas, veo que su utilización es vital en caso de desarrollar proyectos en grupos y queramos hacerlo en tiempo real. En cuanto las conexiones remotas, como SSH y sesiones colaborativas cabe resaltar que se han llevado a cabo de forma satisfactoria. Por úlitmo acerca TypeScript, decir que nunca había realizado ningún proyecto en dicho lenguaje, me parece bastante asequible en cuanto a difucultad por el momento.

## Bibliografía
- Guión de la Práctica - https://ull-esit-inf-dsi-2021.github.io/prct02-vscode/
- Visual Studio Code - https://es.wikipedia.org/wiki/Visual_Studio_Code
- Paquetes Snap de Ubuntu - https://www.profesionalreview.com/2016/04/21/conoce-los-paquetes-snap-ubuntu/
- VSCode Extension Marketplace - https://code.visualstudio.com/docs/editor/extension-gallery
- Remote SSH: Tips and Tricks - https://code.visualstudio.com/blogs/2019/10/03/remote-ssh-tips-and-tricks
- Live Share Extension Pack - https://visualstudio.microsoft.com/es/services/live-share/
- TypeScript - https://es.wikipedia.org/wiki/TypeScript
- Configurar un proyecto para usar TypeScript - https://desarrolloweb.com/articulos/configurar-proyecto-typescript.html










