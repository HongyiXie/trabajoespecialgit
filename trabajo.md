# Git Local
### Es un software de control de versiones diseñado con el propósito de llevar un registro de los cambios en archivos de computadora y coordinar el trabajo que varias personas realizan sobre archivos compartidos.

## Casi todas las operaciones son locales
* Tienes toda la historia del proyecto ahí mismo, en tu disco local, la mayoría de las operaciones parecen prácticamente inmediatas, no necesita conectarse a un servidor.
* Si quieres ver los cambios introducidos en un archivo entre la versión actual y la de hace un mes, Git hace un cálculo de diferencias localmente, en lugar de tener que pedirle a un servidor remoto que lo haga u obtener una versión antigua desde la red. 
> Comando git diff --base <nombre archivo>: para ver conflictos entre archivos.
> Comando git diff <source-branch> <target-branch>: para ver conflictos entre distintas ramas.
* Puedes trabajar tranquilamente en tu repositorio local y luego subir los cambios. El comando git push origin master, envía los cambios que se han hecho en la rama principal de los repertorios remotos que están asociados con el directorio que está trabajando.
* Y para poder fusionar todos los cambios que se han hecho en el repositorio local trabajando, el comando que se usa es git pull

## Los tres estados
* CONFIRMADO (committed): los datos están almacenados de manera segura en tu base de datos local. 
* MODIFICADO (modified): has modificado el archivo pero todavía no lo has confirmado a tu base de datos.
* PREPARADO (staged): has marcado un archivo modificado en su versión actual para que vaya en tu próxima confirmación.

# Fundamentos Basicos de Git
## Obteniendo un repositorio en Git
Puedes obtener un proyecto Git de dos maneras 
1. Tomar un proyecto o directorio existente e importarlo en Git.
2. Clonar un repositorio existente en Git desde otro servidor.

## Inicializando un repositorio en un directorio existente
Si estas empezando a seguir un proyecto existente en Git, debes ir al directorio y usar el siguiente comando: *git init*
Esto crea un subdirectorio nuevo llamado .git, el cual contiene todos los archivos necesarios del repositorio- un esqueleto de un repositorio de Git. Todavia no hay nada en tu proyecto que este bajo seguimiento
Luego ponemos: *git add* **nombre del archivo**
Para especificar que archivos quieres controlar, seguidos de un *git commit* para confirmar los cambios:
Al confirmar los cambios puedes agregar un mensaje, el cual es una breve descripcion de cuales fueron los cambios hechos, para que otros colaboradores puedan saber ¿Que hiciste? y ¿Para que?
Ej: *git commit -m* **Mensaje descriptivo**
## Clonando un repositorio existente
Si deseas obtener una copia de un repositorio git existente, por ejemplo, un proyecto en el que te gustaria contribuir el que comando que necesitas es *git clone* **URL**
## Guardando cambios en el repositorio
Cada archivo de tu repositorio puede tener dos estados:
* Rastreados (tracked files): Todos aquellos archivos que estaban en la ultima instantanea del proyecto.
* Sin rastrear: Cualquier otro archivo en tu directorio de trabajo que no estaba en tu ultima instantanea y que no estan en el area de preparacion (staging area).

Cuando CLONAS por primera vez un repositorio TODOS ESTAN RASTREADOS.

El comando *git status*: te permite conocer en que estado se encuentra el proyecto y en que rama (branch) se encuentra
Si agrego un archivo aparece----"Untracked files" (Archivos no rastreados), son archivos que no tenias en el commit anterior, y aparecen en color rojo

## Rastrear archivos nuevos
Para agregarlos se debe colocar
*git add* **nombre del archivo**

Este comando puede recibir tanto una ruta de archivo como de un directorio; si es de un directorio, el comando añade recursivamente los archivos que estan dentro de el.

## Preparar archivos modificados
*git add. git add* es un comando que cumple varios propositos, lo usas para empezar a RASTREAR archivos nuevos, PREPARAR archivos y hacer otras cosas como MARCAR COMO RESUELTO archivos en conflicto por combinacion.

## Ramificaciones en Git
Una rama Git es simplemente un apuntador movil apuntando a una de esas confirmaciones. 
La rama por defecto de Git es la rama *master*, con la primera confirmacion de cambios que realicemos, se creara esta rama principal *master* apuntando a dicha confirmacion.
En cada confirmacion de cambios que realicemos, la rama ira avanzando automaticamente

### Crear una rama nueva
¿Que sucede cuando creas una nueva rama? Simplemente se crea un nuevo apuntador para que lo puedas mover libremente

Para crear una rama: *git branch* **nombre de la rama**

Eliminar una rama: *git branch -d* **nombre de la rama**

Para saltar de una rama a la otra se ultiliza el comando:

*git checkout* **nombre de la rama**
La rama en el cual estamos trabajando se encuentra especificado al final de color celeste

Con el comando *git log* se nos proporcionara una lista cronologica de cambios realizados detalladamente sobre el proyecto; e indica en que rama esta trabajando, con el apuntador HEAD **nombre de la rama**

El comando *git merge* **nombre de la rama**: incorpora los cambios a la rama master para ponerlos en produccion

# Git remoto

