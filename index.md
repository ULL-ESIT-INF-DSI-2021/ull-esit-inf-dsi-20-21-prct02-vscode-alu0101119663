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
