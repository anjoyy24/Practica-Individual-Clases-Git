
# **CLASE 1 - INTRODUCCIÓN A GIT**
## ¿Qué es un control de versiones?
Un historial de cada cambio que se realiza del código fuente de un proyecto

<img src="https://pistachitos.com/wp-content/uploads/2017/09/cvs.png" width="300" height="200">

### ¿Por qué es tan importante?
* **Rendimiento**
* **Seguridad**. Todo lo que guarde podré recuperarlo
* **Flexibilidad**

## GIT
<img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcSdd25hyNQOMs4Xx1Cv_A_oaT0zagfSWlXMBA&s" width="400" height="200">

## Historia

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

### Comandos extra aprendidos
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

<img src="https://cdn.hashnode.com/res/hashnode/image/upload/v1657263056044/eG4yyw-JN.png" width="300" height="200">

## ¿Qué es un commit?
Es el registro de cambios en el repositorio, da detalles como la fecha, hora, autor y entre otras cosas más.

<img src="https://www.oscarblancarteblog.com/wp-content/uploads/2014/09/commitsimple.png" width="380" height="200">

## Creando commits:
`git commit ` ⮕ Guarda un conjunto de cambios en el historial del repositorio
Cuando escribo este comando me direccionará a un IDE, en este caso el VSC allí debo escribir la etiqueta que quiero que tenga mi commit, este mensaje debe ser claro, describiendo los cambios o actualizaciones que se hicieron.

`git commit -m "Mensaje" ` ⮕ Lo mismo que el `git commit`pero en este caso pongo el mensaje desde git  

`git commit --amend -m "NuevoMensaje" `  ⮕ Renombra el texto del commit ya generado, pero cambia el identificador y solo se puede hacer esto del último commit.

## ¿Qué es el HEAD?
Es un puntero del commit actual en el que se está trabajando. Es como un indicador que te dice algo así como: "Estás aquí" en un mapa.

## ¿Qué es una rama?
Es un nuevo apuntador hacia una de las confirmaciones. 
Es como una linea paralela dentro de mi repositorio, estas permiten realizar un desarrolo lineal y colaborativo.

<img src="https://miro.medium.com/v2/resize:fit:801/1*DhagidpZutkaCmAZobmzDQ.png" width="500" height="250">

## Creando y manejando ramas:
`git branch nombreRamaNueva` ⮕ Crea una rama

`git branch`⮕ Indica en qué rama estoy

`git checkout nombreRama` y `git switch nombreRama` ⮕ Para cambiar rama

`git branch -m nombreRamaActual nombreNuevo` ⮕ Cambia el nombre de una rama

`git branch -d nombreRama` ⮕  Para eliminar la rama

`git branch NuevaRama a4b5c6d` ⮕ Para crear una nueva rama en el commit. El `a4b5c6d` es el identificador del commit

`git switch -c nuevaRama` ⮕  Se usa para crear y cambiar a una rama al mismo tiempo


## Comandos extra aprendidos
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

<img src="https://www.bogotobogo.com/cplusplus/images/Git/Fast_Forward_Merge/FastForwardMerge.png" width="190" height="280">


* **No fast forward.** Permite forzar la creación de un commit de merge incluso en situaciones donde un fast-forward sería posible.

<img src="https://www.bogotobogo.com/cplusplus/images/Git/Fast_Forward_Merge/FastForwardMergeWith_no_ff.png" width="190" height="280">

## Eliminando ramas
### ¿Por qué?
En el momento en el que la otra rama fue fusionada seguirá existiendo, por lo tanto podemos borrarla si ya no es necesario su uso.

`git branch -d` ⮕ Elimina si ya se hizo el merge

`git branch -D` ⮕ Se usa cuando quiero forzar el borrado de la rama incluso si aún no se hizo el merge


Borrar ramas es una buena práctica :3

## Conflictos en git

<img src="https://agbeltran.github.io/git-novice-es/fig/conflict.svg" width="400" height="300">

Un conflicto ocurre en git cuando git no sabe como combinar cambios de dos ramas porque ambas modificaron la misma parte del mismo archivo.
¿Cómo se resuelve?
* Elegir una versión de entre las dos
* Combinar ambas
* Escribir algo nuevo

Luego de hacer los cambios, añadir de nuevo el commit y luego crear un nuevo commit


## Comandos extra aprendidos
<img src="https://i.ytimg.com/vi/MlVtzWL2uRs/hq720.jpg?sqp=-oaymwEhCK4FEIIDSFryq4qpAxMIARUAAAAAGAElAADIQj0AgKJD&rs=AOn4CLDQY3d6LH33WU0VW1f1lELJj04Dug" width="100" height="80">
`git merge --edit` ⮕ Abre el editor antes de hacer el commit

`git merge --no commit` ⮕ Evita que haga commit automáticamente

```
git checkout ramaAMover     //me pongo en la rama que quiero mover 
git rabase main             //Aqui reaplica los commits de la otra rama encima de main, o sea se reescriben los commits
```


# Clase 4 - GIT HUB, PUSH, PULL Y PULL REQUEST
 
 ## Diferencia entre git y github

<img src="https://d1jnx9ba8s6j9r.cloudfront.net/blog/wp-content/uploads/2017/12/gitHub.png" width="450" height="290">
 
 * **Git.** Es un controlador de versiones.
 * **GitHub. **ES un servicio de alojamiento en la nube, ejemplo: bitbucket, gitLab, gitHub, entre otros.

 ## Repositorios remotos
 Es una copia de mi proyecto en la nube (los servidores de GitHub) y que puedo sincronizar con mi repositorio local.

 ### Enlazar un repositorio local con un repositorio remoto
 `git remote add Origin URLDelRepo` ⮕ Enlaza, el `origin` es el nombre del alias es como un estándar de nombre para un alias

`git clone URLdelRepositorio` ⮕ Sirve para clonar

 ### Generar llaves SSH
 Estas proporcionan un método de autenticidad seguro y conveniente para acceder a ramas remotas.

### Sincronizando con un repositorio remoto
* **PUSH.**
`git push Origin Rama` ⮕ Sirve para enviar los commits de mi repositorio local a un repositorio remoto

* **PULL.**
`git  pull` ⮕ Trae todos los cambios del repositorio remoto al repositorio actual
    
    El `git pull` es una mezcla de dos comandos:
    * `git fetch` ⮕ Descarga commits y referencias del repositorio remoto al local
    * `git merge` ⮕ Es el que fisiona la rama remota obtenida con la rama local actual

### Crear rama remota
Para esto la rama debe de existir en el repositorio local y se sube al repositorio remoto con: `git push -u origin nombreRama`

### Eliminar ramas de mi repositorio local que no se usan
`git remote prune origin` ⮕ Elimina referencias locales a ramas remotas que ya no existen en el repositorio remoto 

## Pull request
Un pull request o PR es una solicitud de revisión del código

<img src="https://wac-cdn.atlassian.com/dam/jcr:dc1a0821-efd6-4852-b7e6-c3a787656c61/02.svg?cdnVersion=2705" width="600" height="200">

**¿Cómo hacer un pull request?**
* GitHUb me mostrará una opción que dice "Compare & pull request" cuando subo la rama
* Elijo la rama base y la rama de comparación
* Se agrega un título y una descripción
* Y por último sigue la revisión del equipo, donde los miembros del equipo pueden comentar, sugerir cambios, aprobar o rechazar 


## Comandos extra aprendidos
<img src="https://i.ytimg.com/vi/MlVtzWL2uRs/hq720.jpg?sqp=-oaymwEhCK4FEIIDSFryq4qpAxMIARUAAAAAGAElAADIQj0AgKJD&rs=AOn4CLDQY3d6LH33WU0VW1f1lELJj04Dug" width="100" height="80">

`git branch -a` ⮕Permite revisar ramas que existen en un repositorio remoto

 `git remote` ⮕ Para ver el alias

`git remote -v` ⮕ Indica el alias y a que URL está apuntando


# Clase 5 - GITFLOW
## Modelos de trabajo
### 1. GitFlow
Es la manera en la que el equipo de desarrolo va a utilizar Git para trabajar de manera colaborativa, en sí es un flujo de trabajo.

<img src="https://miro.medium.com/v2/resize:fit:1400/1*3-0EDzE63S_UZx2KbIz_dg.png" width="400" height="200"> 

GitFlow usa las siguientes ramas:
* Main ⮕ Con el código de producción
* Develop ⮕ Código que tiene que ser validado y probado
* Feature ⮕ Características nuevas para el proyecto
* Release ⮕ Cambios de último momento
* HotFix ⮕ Parches o arreglar pequeños bugs
### 2. GitHub Flow

<img src="https://miro.medium.com/v2/resize:fit:1400/1*3-0EDzE63S_UZx2KbIz_dg.png" width="400" height="200"> 

* Solo se basa en main y ramas de funcionalidad 
* Se usa cuando hay una integración continua (CI)
### 3. Trunk-Based Development
Es cuando solo hay una rama principal, hay ramas de funcionalidad pero son cortas

<img src="https://www.travis-ci.com/wp-content/uploads/2024/04/what-is-tbd-1024x459.gif" width="400" height="200"> 


Aqui se muestra una tabla de diferencias:

| **Característica** | **Git Flow** | **GitHub Flow** | **Trunk-Based Development** |
|--------------------| ------------ | ----------------| --------------------------- |
| Modelo de ramas | Múltiples ramas (`main`, `develop`, `feature`, `release`, `hotfix`) | `main` + ramas de feature | Solo `main` (y ramas muy cortas si se usan) |
|  Uso  | Versiones planificadas | Despliegue continuo  | Integración y despliegue continuo |
| Tiempo de integración | Semanal o por versión  | Diaria o por cambio | Varias veces al día |
| Duración de ramas | Larga | Corta  | Muy corta (horas o 1-2 días) |
| Ejemplo de ramas típicas  | `main`, `develop`, `feature/login`, `release/1.0`, `hotfix/bug`     | `main`, `feature/login`               | `main`, (ocasionalmente `feature/login`)    |

## Compartir cambios según el contexto

<img src="https://midu.dev/images/ship-show-ask.png" width="600" height="300"> 

Para esto existen 3 formas, según el contexto, riesgo y urgencia, son los siguientes
* **Ship.** Fusiona en la rama sin revisión previa.
* **Show.** Abre una petición para que sean revisados por CI pero se fusiona inmediatamente
* **Ask.** Abre una PR para discutir los cambios antes de fusionarlos

# Clase 6 - BUENAS PRÁCTICAS

<img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcS3yya5v7KstUz8E4-YCRVfVxlC4m3VOuYhOA&s" width="200" height="200">

## ¿Por qué son importantes?
* Funcionan como un estándar para la legibilidad
* Resuelven conflictos durante el desarrollo
* El historial de commits es más legible

## Buenas prácticas en commits
### ¿Cada cuánto se debe hacer un commit?**
A menudo, pero que sean commits necesario y que no sean sin sentido.
### Escribir buenos commits
* Usar verbos imperativos preferiblemente en inglés (fix, add, remove, change)
* Sin signos de puntuación a parte de ","
* Máximo 50 carácteres para un commit
* Formato común: `<tipo-de-commit>[scope-¿Dónde?]<descripción>`
#### Prefijos de commits
* **feat.** para nueva caterística 
* **fix.** para corregir un bug
* **docs.** para documentación
* **refactor.** para refactorización de código
* **test.** para test 

## Buenas prácticas en ramas
### Escribir buenos nombres para las ramas
Las ramas deben de tener nombres descriptivos
Ejemplo:

`bug/avoid-creating-load-twice`

`hotfix/fix-typo-in-name`
#### Convenciones comunes
`feature/` ⮕ Para nuevas funcionalidades

`bugfix/` ⮕ Para corrección de errores

`hotfix/` ⮕ Para errores críticos en producción

`test/` ⮕ Para pruebas

`docs/` ⮕ Para documentación

# Clase 7 - DESHACER CAMBIOS
Se deshace cambios cuando el proyecto deja de funcionar, cuando queremos recuperar una parte del código que eliminamos o cuando queremos recuperar archivos que eliminamos.

<img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcRrZKtxKp-sbtReV27kpuTHvPsEHTy71hKjIg&s" width="200" height="200">

## Comandos destructivos
Afectan el historial de los commits realizados

<img src="https://cdn-icons-png.flaticon.com/512/7462/7462471.png" width="200" height="200">

## Comandos no destructivos
Trabajan en base al historial sin afectarlo


 
### GIT RESET
**No destructivo:**

`git reset --soft` ⮕ Deshace commit, mantiene stanging y archivos

`git reset --mixed` ⮕ Deshace commit, mantiene archivos, borra stanging

**Destructivo:**

`git reset --hard` ⮕ Borra commit, staging y archivos locales

`git reset --hard` + push ⮕ Modifica historia remota (Peligrosooo!)

### GIT REVERT
Es un comando **no destructivo** que se usa para deshacer un commit ya realizado, pero en lugar de eliminarlo del historial crea un nuevo commit que revierte los cambios del commit original


`git revert <id-del-commit>` ⮕ Deshace el commit, no borra el historial y es seguro para la colaboración

# Clase 8 - HOOKS, ALIAS Y TRUCOS EN GIT
## ¿Qué es un hook?
Son scripts que se ejecutan automáticamente en eventos de git 
HOOKS = Automatización

<img src="https://miro.medium.com/v2/resize:fit:450/1*bAJrSit_8HoM5sy7ydw0zw.png" width="300" height="150">

### Hooks del lado del cliente
Se encuentra en: .git/hooks/
Estos se ejecutan en la máquina del desarrollador, durante operaciones locales como los commits, cambios de ramas, merges y entre otros más
Hooks del lado del cliente:
* `pre-commit` ⮕ Se usa para lint, tests, formateo, se ejecuta antes de hacer un commit

* `prepare-commit-msg` ⮕ Autogenera mensajes, se ejecuta antes de escribir mensaje de commit

* `commit-msg` ⮕ Valida el formato del mensaje, se ejecuta después de escribir el mensaje

* `post-commit` ⮕ Se usa para notificaciones y logs, se ejecuta después de hacer un commit

* `post-checkout` ⮕ Se usa para configurar el entorno y limpiar cachés, se ejecuta después de cambiar de rama

* `post-merge` ⮕ Se usa para reinstalar dependencias, se ejecuta después de el merge

* `pre-push` ⮕ Se usa para Test y revisión de código, se ejecuta antes de hacer git push


 <img src="https://d8it4huxumps7.cloudfront.net/uploads/images/652f8091f32cc_git_hooks_06.jpg?d=2000x2000" width="500" height="200">
 
### Hooks del lado del servidor 
Se ejecutan en el servidor (como GitHub)durante el push o receive entre otroos
Hooks del lado del servidor:
* `pre-receive` ⮕ Para verificar que los commits que están para ser guardados están bien formados y que el usuario tiene permisos para grabar los commits.

* `update` ⮕ Verifica cambios específicos en ramas, se ejecuta una vez por cada rama que se está actualizando en un push

* `post receive` ⮕ Envía notificaciones (email, discord...)

### Crear un hook
* Crear un archivo: `nombre-del-hook`
* Poner el archivo en la carpeta `.git/hooks`
* Y en el poner el código a ejecutar


## Alias

### ¿Qué es un alias?
Son comandos cortos personalizados, son atajos para comandos largos
Ejemplos:
* De `status` ⮕ `st` 
* De `commit` ⮕ `co`

### Creando un alias
`git config --global alias.<alias> 'comando'`

Aplicando:

`git config --global alias.st "status"`

`git config --global alias.co "commit"`

## Trucos en Git

### Guardar cambios temporalmente
* `git stash` ⮕ Guarda cambios no commiteados
* `git stash -u`⮕ Guarda cambios no commiteados y archivos sin seguimiento
* `git stash pop` ⮕ Restaura los cambios guardados con stash y elimina esa entrada del stash

### Aplicar cambios de commits en específico
`git cherry-pick <SHA>` ⮕ Aplica un commit específico de otra rama al historial actual 

### Detectar qué commit es el que ha introducido un bug

<img src="https://w7.pngwing.com/pngs/524/102/png-transparent-software-bug-computer-programming-programmer-software-testing-error-cartoon-computer-cartoon-character-hand-computer-thumbnail.png" width="300" height="200">

* `git bisect` ⮕ Comienza una búsqueda binaria para encontrar un commit que introdujo un bug
* `git bisect start` ⮕ Inicia el proceso de bisect
* `git bisect bad`⮕ Marca el commit actual com problemático
* `git bisect good` ⮕ Marca un commit anterior como correcto
* `git bisect reset` ⮕ Sale del modo bisect y vuelve al estado original del repositorio

### Cambiar nombre de un commit
* `git commit --amend -m <descripcion-commit>` ⮕ Cambia el mensaje del último commit 
### Recuperar un archivo en concreto de otra rama o commit
* `git checkout <SHA><archivo>` ⮕ Recupera una versión específica de un archivo desde otro commit o rama


