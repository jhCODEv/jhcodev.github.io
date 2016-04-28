---
layout: post
title: Configurando acceso SSH en SourceTree para GitHub y Bitbucket para Windows
---



## Crear una llave SSH



#### 1) Ejecutar ssh-keygen
```
$ shh-keygen
```

#### 2) Indicar ubicacion y nombre de la llave

Nos va a pedir donde y como se van a llamar las llaves que se van a generar. 
Si no indicas nada, va a guardar las llaves en la carpeta .ssh del usuario logueado y 
con el nombre id_rsa. En este caso le indico que lo grabe en E:\>ssh\sourcetre_rsa 

```
$ Enter file in which to save the key (/c/Users/your_user_name/.ssh/id_rsa): /e/ssh/sourcetree_rsa
```

#### 3) Indicar passphrase

Un passphrase es como un password pero mas largo, haciendolo mas seguro.
Complementa la seguridad de la llave generada al ser requerida cada vez 
que la utilizamos. Esto nos protege en el caso de que alguien acceda a nuestro
sistema (donde esta la llave privada) y sin ningun tipo de autorizacion haga uso de
todos los servicios "protegidos" por la misma. Sin la passphrase no va a poder hacer nada.
Es el metodo mas seguro pero tambien engorroso, a menos que utilizemos *ssh-agent*, un
programita que guarda de forma segura el passphrase y lo inserta automaticamente cuando
se lo necesita.

```
Enter passphrase (empty for no passphrase):
Enter same passphrase again:  
```

#### 4) Finalmente...

Si todo sale bien, se van a generar las llaves (publica y privada) y vas a ver lo siguiente:

```
Your identification has been saved in /e/ssh/sourcetree_rsa.
Your public key has been saved in /e/ssh/sourcetree_rsa.pub.
The key fingerprint is:
SHA256:asdjlkwnwqoaksdjdnakasdiwji213909232jssajks lalalala@lalalala-PC
The key's randomart image is:
+---[RSA 2048]----+
|.................|
|++ + ++++ +++ ++ |
|                 |
|o.o.o.o.o.o.o. o.|
|. o            ..|
|o++  ++++    +++o|
|.... * * .o...o+*|
|.** * == 00     =|
|........   ...   |
+----[SHA256]-----+
```

#### 5) Todo en un GIF:

![_config.yml]({{ site.baseurl }}/images/201604271/1.gif)

## Crear un archivo de configuracion SSH

Tenes que crear un archivo llamado **config** (si es que no existe) en el path 
**C:/Users/your_user_name/.ssh/** con el siguiente contenido:

```
Host bitbucket.org
 IdentityFile E:\>shh\sourcetree_rsa
```

![_config.yml]({{ site.baseurl }}/images/201604271/2.gif)

## Agregar la clave publica a GitHub o a Bitbucket

## Configurar SourceTree con la llave privada


