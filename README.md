
# **CLASE 1 - INTRODUCCIÓN A GIT**
## ¿Qué es un control de versiones?
Un historial de cada cambio que se realiza del código fuente de un proyecto

<img src="https://unity.com/_next/image?url=https%3A%2F%2Fcdn.sanity.io%2Fimages%2Ffuvbjjlp%2Fproduction%2F1e2f049c087a0e525585f6108abdaaaba0befd9b-1920x1080.jpg&w=3840&q=75" width="300" height="200">

### <p style="color:#b833ff;">¿Por qué es tan importante?.</p>
* **Rendimiento**
* **Seguridad**. Todo lo que guarde podré recuperarlo
* **Flexibilidad**

## GIT
<img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSdd25hyNQOMs4Xx1Cv_A_oaT0zagfSWlXMBA&s" width="400" height="200">

## <p style="color:#b833ff;">Historia.</p>

* **1990 ⮕** CVS era el primer controlador de versiones (no usaba ramas, era lineal)
* **2002 ⮕** Se usaba bitkeeper como controlador de versiones
* **2005 ⮕** Bitkeeper dejó de ser gratuita - Creación de Git por Linus Torvalds
* **2008 ⮕** Creación de GitHub
* **2018 ⮕** Microsoft compra GitHub, pero seguía siendo gratuita
* **2024 ⮕** Git domina el mercado


## ¿Qué es GIT?
Es un sistema de control de versiones distribuido, digamos que estoy trabajando en un documento importante y cada vez quiero guardar una copia con una etiqueta que describa la versión, eso es lo que hace GIT.

## ¿Qué es un repositorio?
Es donde se almacena el historial de cambios de un proyecto junto con otro tipo de archivos
### <p style="color:#b833ff;">Tipos de repositorios</p>

<img src="https://i0.wp.com/www.julianmarquina.es/wp-content/uploads/No-basta-con-depositar-hay-que-visibilizar.jpg?fit=1000%2C673&ssl=1" width="400" height="200">

* **Local.** Se encuentra en nuestro ordenador.
* **Remoto.** Se encuentra en un servidor externo, un ejemplo de un servidor central sería GitHub

### <p style="color:#ff8333;">Comandos extra aprendidos.</p>
<img src="https://i.ytimg.com/vi/MlVtzWL2uRs/hq720.jpg?sqp=-oaymwEhCK4FEIIDSFryq4qpAxMIARUAAAAAGAElAADIQj0AgKJD&rs=AOn4CLDQY3d6LH33WU0VW1f1lELJj04Dug" width="100" height="80">

`git init` ⮕ Sirve para creaer un respositorio en el directorio actual.

`git --help` ⮕ Accede a la documentación de Git.
___
___
# Clase 2 - STATE Y COMMITS
## Estados de Git
* **Modified.** Es cuando el archivo fue creado, eliminado o cambiado, no están marcados como confirmados.
* **Staged.** El archivo ha sido marcado como preparado para el commit que se puede crear. 
* **Commited.** Los cambios son guardados en el repositorio local.

## ¿Qué es un commit?
Es el registro de cambios en el repositorio, da detalles como la fecha, hora, autor y entre otras cosas más.
## <p style="color:#33c4ff;">Creando commits:</p>
`git commit ` ⮕ Guarda un conjunto de cambios en el historial del repositorio
Cuando escribo este comando me direccionará a un IDE, en este caso el VSC allí debo escribir la etiqueta que quiero que tenga mi commit, este mensaje debe ser claro, describiendo los cambios o actualizaciones que se hicieron.

`git commit -m "Mensaje" ` ⮕ Lo mismo que el `git commit`pero en este caso pongo el mensaje desde git  

`git commit --amend -m "NuevoMensaje" `  ⮕ Renombra el texto del commit ya generado, pero cambia el identificador y solo se puede hacer esto del último commit.

## ¿Qué es el HEAD?
Es un puntero del commit actual en el que se está trabajando. Es como un indicador que te dice algo así como: "Estás aquí" en un mapa.

## ¿Qué es una rama?
Es un nuevo apuntador hacia una de las confirmaciones. 
Es como una linea paralela dentro de mi repositorio, estas permiten realizar un desarrolo lineal y colaborativo.

## <p style="color:#33c4ff;">Creando y manejando ramas:</p>
`git branch nombreRamaNueva` ⮕ Crea una rama

`git branch`⮕ Indica en qué rama estoy

`git checkout nombreRama` y `git switch nombreRama` ⮕ Para cambiar rama

`git branch -m nombreRamaActual nombreNuevo` ⮕ Cambia el nombre de una rama

`git branch -d nombreRama` ⮕  Para eliminar la rama

`git branch NuevaRama a4b5c6d` ⮕ Para crear una nueva rama en el commit. El `a4b5c6d` es el identificador del commit

`git switch -c nuevaRama` ⮕  Se usa para crear y cambiar a una rama al mismo tiempo


## <p style="color:#ff8333;">Comandos extra aprendidos.</p>
<img src="https://i.ytimg.com/vi/MlVtzWL2uRs/hq720.jpg?sqp=-oaymwEhCK4FEIIDSFryq4qpAxMIARUAAAAAGAElAADIQj0AgKJD&rs=AOn4CLDQY3d6LH33WU0VW1f1lELJj04Dug" width="100" height="80">

`git status` ⮕ Muestra el estado actual del repositorio, muestra:
* La rama actual
* Los archivos listos
* Los archivos modificado

`git add nombreArchivo ` ⮕ Agrega cambios en archivos al estado staged

`git add . ` ⮕ Permite agregar todos los cambios de archivos modificados o nuevos al estado staged

`git restore ` ⮕ Deshace los cambios del código local

`git restore --staged nombreArchivo` ⮕ Quita el archivo el staging

`git log` ⮕ Muestra el historial de commits que hay en el repositorio

`git log -h `⮕ Muestra la lista de parametros para poder usar el `git log`

`git log --h`  ⮕ Documentación

`git log --oneline`  ⮕ Muestra un resumen del historial de commits

`&&` ⮕  Sirve para concatenar comandos
___
___
# Clase 3 - RAMAS, MERGE Y CONFLICTOS
Las ramas pueden acabar de dos maneras:
* Acabar en el olvido
* Ser fusionada con otra rama

## Fusión de ramas
Es el proceso en el cual se integran los cambios de una rama en otra

`git merge ramaAFusionar` ⮕ Sirve para fusionar ramas

Al ejecutar `git merge`  se crea un nuevo commit que incluye todos los cambios de la rama de origen a la rama en la que nos encontramos ahora.

* **Fast forward.** Cuando hago el `git merge`, Git compara el historial de la rama en la que estoy con la rama que quiero fusionar. Si la rama no contiene commits nuevos desde que se creó la otra rama, git simplemente adelanta el puntero.

![](https://www.bogotobogo.com/cplusplus/images/Git/Fast_Forward_Merge/FastForwardMerge.png)

* **No fast forward.** Permite forzar la creación de un commit de merge incluso en situaciones donde un fast-forward sería posible.

![](https://www.bogotobogo.com/cplusplus/images/Git/Fast_Forward_Merge/FastForwardMergeWith_no_ff.png)

## Eliminando ramas
### ¿Por qué?
En el momento en el que la otra rama fue fusionada seguirá existiendo, por lo tanto podemos borrarla si ya no es necesario su uso.

`git branch -d` ⮕ Elimina si ya se hizo el merge

`git branch -D` ⮕ Se usa cuando quiero forzar el borrado de la rama incluso si aún no se hizo el merge

Borrar ramas es una buena práctica :3

## Conlflictos en git
Un conflicto ocurre en git cuando git no sabe como combinar cambios de dos ramas porque ambas modificaron la misma parte del mismo archivo.
¿Cómo se resuelve?
* Eelgir una versión de entre las dos
* Combinar ambas
* Escribir algo nuevo

Luego de hacer los cambios, añadir de nuevo el commit y luego crear un nuevo commit


## <p style="color:#ff8333;">Comandos extra aprendidos.</p>
<img src="https://i.ytimg.com/vi/MlVtzWL2uRs/hq720.jpg?sqp=-oaymwEhCK4FEIIDSFryq4qpAxMIARUAAAAAGAElAADIQj0AgKJD&rs=AOn4CLDQY3d6LH33WU0VW1f1lELJj04Dug" width="100" height="80">
`git merge --edit` ⮕ Abre el editor antes de hacer el commit

`git merge --no commit` ⮕ Evita que haga commit automáticamente

```
git checkout ramaAMover     //me pongo en la rama que quiero mover 
git rabase main             //Aqui reaplica los commits de la otra rama encima de main, o sea se reescriben los commits
```






