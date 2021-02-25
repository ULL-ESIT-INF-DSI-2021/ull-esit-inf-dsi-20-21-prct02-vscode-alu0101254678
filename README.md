# Desarrollo de Sistemas Informáticos
## Práctica 2 - Instalación y Configuración de Visual Studio Code
## Yago Pérez Molanes
__*Contenidos del informe*__

__*Pasos realizados para el desarrollo de la práctica*__
* Algunas tareas a realizar previamente:
	* Aceptar la tarea asignada a [GitHub Classroom](https://classroom.github.com/assignment-invitations/aeecb6b9d939b7fd914ea3c40d832362/status) asociada a esta práctica.
	* Leer la [introducción a Markdown](https://guides.github.com/features/mastering-markdown/).Este es el lenguaje que se usará en el desarrollo del presente informe.
	* Lectura del recurso [GitHub Pages](https://docs.github.com/en/github/working-with-github-pages), ya que el presente informe se presentará a modo de una página web de GitHub.
      
## __Introducción y Objetivos__
En esta llevaremos a cabo la instalación y la configuración del entorno de desarrollo que usaremos durante las prácticas, Visual Studio Code.

Cuando finalicemos el desarrollo tendremos a punto el IDE para ayudarnos a realizar las siguientes prácticas.

## __Instalación y funcionalidad de Visual Studio Code__
El entorno de desarrollo que vamos a usar en las prácticas es [Visual Studio Code](https://code.visualstudio.com/).Lo primero que deberemos hacer será [instalarlo](https://code.visualstudio.com/docs/setup/setup-overview) en nuestra máquina local.

Si tuvieramos una distribución Linux *Debian/Ubuntu* la instalación se reduciría a los siguientes comandos en una terminal:

```markdown
yago@yago-X541UJ:~$ sudo apt install code

```
Es posible que nos pida la contraseña de nuestra cuenta.
También se puede hacer uso de *snap* para instalar code 

```markdown
yago@yago-X541UJ:~$ sudo snap install code --classic

```

Una vez que tenemos code instalado podemos ejecutarlo en el escritorio o en el menú de aplicaciones, o incluso con el comando *code*, en una terminal, a la vez que podemos indicarle como argumento alguno de los directorios sobre los que queremos trabajar.

Este es el aspecto que tendría code según lo ejecutamos.

![captura_code_1](/img/captura_code_1.png)


## __Conexión a una máquina virtual ssh con Visual Studio Code__
Vamos a llevar a cabo la configuración necesaria para [conectarnos](https://code.visualstudio.com/docs/remote/ssh-tutorial) desde Visual Studio Code a la máquina virtual del *IaaS*, a través de una conexión *ssh*.

Recordamos que de la práctica anterior tenemos configurada la máquina virtual del IaaS, entonces podemos establecer una configuración VPN si no nos encontramos en la red universitaria y conectarnos por *ssh* en una terminal.

Sin embargo también podemos hacerlo desde Visual Studio Code, a través de una [extensión](https://code.visualstudio.com/docs/editor/extension-gallery)

Una extensión es una funcionalidad que se puede añadir a Visual Studio Code, nosotros vamos a instalar __Remote SSH__:
![captura_code_3](/img/captura_code_3.png)

Seguidamente, deberemos pulsar la tecla __F1__ o la combinación de teclas __Ctrl + Shift + P__, en el menú desplegable escribimos la orden __ssh__ y después __Connect to host...__.

Recordamos de la anterior práctica que ya habíamos configurado el fichero que contenía la configuración de *ssh*, de ahí que podamos seleccionar el nombre que se indica de la máquina virtual. 

En el caso de que no suceda lo anterior, podemos pulsar sobre la opción __Configure SSH Hosts...__ y elegimos la opción __~/.ssh/config__, incluyendo las siguientes líneas:

```markdown
Host iaas-dsi15
  HostName iaas-dsi15
  User usuario
```
Como vemos la máquina es *iaas-dsi-15* que es la que nos había asignado el *iaas* y el usuario no lo hemos cambiado, sino que lo hemos dejado por defecto.Sin embargo, para cada máquina esta tendrá un nombre distinto.

Una vez seguidos estos pasos, lo siguiente será la opción __Connect to Host__ cuando volvamos a abrir el menú desplegable con __F1__, en este caso seleccionamos la máquina virtual, y nuestras credenciales, esto es, la contraseña para el usuario que hemos añadido en el fichero de configuración anterior.

Esto originará una nueva ventana del Visual Studio Code, que iniciará la conexión remota, podemos abrir una terminal desde el propio Code, con la combinación de teclas __Ctrl + Shift +__.En la terminal podemos teclear el siguiente comando:

```markdown
[~/ull-esit-inf-dsi-20-21-prct02-vscode-alu0101254678/docs(master)]$hostname
iaas-dsi15
[~/ull-esit-inf-dsi-20-21-prct02-vscode-alu0101254678/docs(master)]$
```

Como se puede observar, dicho comando devuelve el nombre de host de la máquina virtual remota. En la esquina inferior izquierda, se puede observar el nombre de la máquina virtual al que estamos concetados.

![captura_code_4](https://github.com/ULL-ESIT-INF-DSI-2021/ull-esit-inf-dsi-20-21-prct02-vscode-alu0101254678/blob/master/img/captura_code_4.png)

## __Live Share en Visual Studio Code (sesiones colaborativas)__

Visual Studio Code permite trabajar con otras personas en tiempo real, gracias a la extensión [Live Share Extension Pack](https://marketplace.visualstudio.com/items?itemName=MS-vsliveshare.vsliveshare-pack) que se puede instalar desde Visual Studio Code.

Cuando nos encontramos en una sesión remota, las extensiones que instalamos desde Code, se quedan ahí, es decir, en la máquina remota, por lo tanto no debemos olvidar en qué lugar estamos instalando las extensiones.

Para instalar una extensión en la máquina local, primero deberemos desconectarnos de la máquina remota, y posteriormente en nuestra máquina podemos proceder a las instalaciones.

Ahora podemos iniciar una sesión colaborativa con otras personas.

## __Nuestro primer proyecto en Typescript, "Hola mundo"__

Antes de nada, vamos a proceder con la instalación de dos extensiones que resultan muy útiles:

* Vim. En el caso de que prefiramos el editor de texto.
* ESlint. Permite realizar comprobaciones de estilo sobre ficheros en los que se incluya código fuente de JavaScript y TipeScript.

Para ello, seguimos los pasos llevados para la instalación de otras extensiones, sin embargo, en el buscador tendremos que escribir *Vim* y *ESLint* y hacer click sobre *install*.

[]()
[]()

Ahora, instalamos el compilador de *Typescript*, recordemos que no solo se trata de un lenguaje de programación, sino que también cumple las funciones de compilador.Para la instalación usaremos __npm__ que es el gestor de paquetes de *Node*.

```markdown
[~/ull-esit-inf-dsi-20-21-prct02-vscode-alu0101254678/docs(master)]$npm install --global typescript

changed 1 package, and audited 2 packages in 3s

found 0 vulnerabilities
[~/ull-esit-inf-dsi-20-21-prct02-vscode-alu0101254678/docs(master)]$tsc --version
Version 4.2.2
[~/ull-esit-inf-dsi-20-21-prct02-vscode-alu0101254678/docs(master)]$
```

La opción *--global* permite instalar el paquete de forma global.

Seguimos en la terminal de visual studio code, y ahora procedemos a escribir los siguientes comandos:

```markdown
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
drwxr-xr-x 13 usuario usuario 4,0K feb 25 17:53 ..
-rw-rw-r--  1 usuario usuario  225 feb 25 17:53 package.json
drwxrwxr-x  2 usuario usuario 4,0K feb 25 17:53 .
[~/hello-world()]$
```

Con el comando *pwd* comprobamos el directorio en el que nos encontramos, seguidamente creamos con *mkdir* un directorio llamado *hello-world* que servirá para nuestro primer proyecto de prueba.

Nos movemos a dicho directorio, y escribimos el comando __*npm init --yes*__ lo que inicia la creación de un fichero llamado __*package.json*__, en donde se gestionan las dependencias de desarrollo y ejecución del proyecto en forma de paquetes	de los que se indica la dependencia.La salida es la que se muestra al final.

Desde Visual Studio Code, es posible abrir un directorio, en este caso, lo haremos con *hello-world*, para, desde el menú __*File*__, en el desplegable seleccionamos la opción __*Open Folder*__ y nuestro directorio, seguidamente se abrirá una instancia y podremos ver el contenido de dicho directorio.

![]()

También es posible añadir el directorio a un espacio de trabajo (*workspace*). Para ello, en el menú __*File*__ nos vamos a  la opción __*Add folder to workspace*__, seleccionando el directorio propiamente nombrado.

En el caso de que no tengamos ningún espacio de trabajo creado previamente, se creará uno nuevo y se añadirá el directorio al mismo. Para guardar el espacio de trabajo se puede hacer seleccionando la opción __*Save Workspace as...*__ del menú __*File*__, escribiendo un nombre de fichero y pulsando sobre el botón __*OK*__.

Creamos un nuevo fichero en el directorio *hello-world*, llamado __*tsconfig.json*__. Es posible hacerlo mediante la terminal de VS Code o el explorador situado a la izquierda.En este fichero es en donde se indican las opciones del compilador de Typscript.Vamos a incluir las siguientes líneas en dicho fichero y a pasar a explicarlas.

```markdown
[~/hello-world()]$vim tsconfig.json 
[~/hello-world()]$cat tsconfig.json 
{
  "compilerOptions": {
    "target": "ES2018",
    "outDir": "./dist",
    "rootDir": "./src",
    "module": "CommonJS"
  }
}
[~/hello-world()]$
```

La primera opción indica al compilador que queremos generar código en la última versión del estándar de *JavaScript*, y como es lógico, podemos indicar otro estándar de *JavaScript*.

En segundo lugar, especificamos el directorio de salida de los ficheros que generemos cuando compilemos el código fuente de Typescript a JavaScript, en este caso, __*dist*__ .En tercer lugar, estamos diciéndole al compilador donde queremos que analice el código fuente, esto es, en __*/src*__.

Por último, se indica un estándar para cargar código fuente desde ficheros independientes.

Ahora, añadiremos un fichero con código en *TypeScript*.Ejecutamos los siguientes comandos en la terminal de VS Code:
```markdown
[~/hello-world()]$pwd
/home/usuario/hello-world
[~/hello-world()]$mkdir src
[~/hello-world()]$ls
package.json  src  tsconfig.json
[~/hello-world()]$cd src
[~/hello-world/src()]$touch index.ts
[~/hello-world/src()]$ls
index.ts
[~/hello-world/src()]$
```

En este punto hemos creado el fichero de código fuente, con el nombre *index.ts*, añadimos las siguientes líneas de código al mismo:

```Typescript
let myString: string = "Hola Mundo";
console.log(myString);
```

En la terminal de Visual Studio Code, podemos compilar nuestro fichero con el sigueinte comando:

```markdown
[~/hello-world()]$tsc
```

Recordamos que en las opciones de compilación habíamos específicado el directorio de salida, por lo tanto en el directorio */dist* tendremos el fichero __*index.js*__.

```markdown
[~/hello-world()]$diff dist/index.js src/index.ts 
1c1
< let myString = "Hola Mundo";
---
> let myString: string = "Hola Mundo";
```

Con el comando __*diff*__ comprobamos las diferencias que existen entre dos ficheros. Encontramos que la principal diferencia está en la declaración de la variable __*my string*__.

Una de las características de *TypeScript*, es la declaración de datos estáticos o *tipado* estático, es decir que se puede indicar el tipo de una variable, por ejemplo si quieremos que sea un entero, una cadena de caracteres, un booleano...

De esta forma se pueden evitar los problemas que ocurren cuando el tipo de una variable se decide en tiempo de ejecución, como sucede en *JavaScript*.

Por último, solo nos queda ejecutar el fichero que se ha generado tras la compilación, __*index,js*__, que, recordemos que podemos ejecutarlo.

Esto se realiza con el comando *node* y la ruta al fichero.

```markdown
[~/hello-world()]$node dist/index.js
Hola Mundo
[~/hello-world()]$
```

## __Conclusiones__

## __Bibliografía__







