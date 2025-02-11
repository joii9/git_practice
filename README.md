# Comandos de GIT

**git init** Inicializa un path en GIT
git checkout				Enlista los archivos modificados

git status				Comprueba el estado de los archivos dentro del repositorio
git add					Agregamos el archivo a stagging area. (.) Agrega todos los archivos. O podemos agregar los archivos especificos que queramos escribiendolo continueamente ex. git add <filename1> <filename2. O podemos agregar los archivos especificos que queramos escribiendolo continueamente ex. git add <filename1> <filename2>
git commit -m "message"			Comando para generear un "checkpoint" un punto con log, un punto al cual se puede volver.
git commit --amend			Este comando es para actualizar el ultimo commit y evitar crear otro commit
git commit --amend -m "message"		Edita el ultimo commit con el nuevo mensaje
git commit --amend --no-edit		Si olvidamos agregar algun archivo a nuestro ultSi olvidamos agregar algun archivo a nuestro ultimo commit, nosotros podemos agregar un archivo al ultimo commit
git diff <filename>			Para revisar cuales son las diferencias del archivo con el ultimo commit
git log					Podemos ver todos los commits o "checkpoints" hechos del repositorio y un identificador SHA de cada commit
git log --oneline			Muestra los logs en una sola linea
git log -n				Limita el numero de log mostrasdos por commits, dependiendo el numero especificado
git log --skip=<number>			Salta el numero de logs recientes. (No muestra los ultimos "n" logs)
git log --author=<author>		Muestra los commits hechos por "author"
git log --grep=<keyword>		Muestra los mensajes de los commits que contengan la palabra buscada
git log --grep=<keyword> --invert-grep	Muestra todos los resultados que NO contentan "keyword"
git show HEAD				Muestra el repositorio actual donde estamos trabajando y sus modificaciones
git reset HEAD <filename>		Este comando es usado para quitar un archivo de la "staging area" o area de preparación para no ser crear un checkpoint en el commit con este archivo.
git restore <filename>			Para restablecer un archivo eliminado del direcotrio de trabajo o descartar los cambios en el archivo
git checkout HEAD <filename>		Para restablecer un version mas vieja en el directorio de trabajo. La version mas vieja es la ultima en el git log y descarta los cambios hechos en stagging area
git checkout --<filename>		Para restablecer un version mas vieja en el directorio de trabajo. La version mas vieja es la ultima en el git log y descarta los cambios hechos en stagging area
git reset <commit_SHA>			Con este comando nosotos podemos regresar a un previo checkpoint con los primeros siete caracteres de un log. Lo que significa que estaremos borrando los checkpoints anteriores pero las modificaciones que se hicieron seguirian visibles en el archivo.


GIT STASH
git stash				Se usa para almacenar en un repositorio oculto (como una pausa) se puede volver a el, esto oculta las ultimas modificaciones del archivo.
git stash apply				Muestra el archivo con las modificaciones ocultas pero no elimina el stash
git stash drop				Elimina el ultimo stash
git stash drop stash@{#}		Elimina un stash en especifico
git stash clear				Elimina todos los stashes
git stash pop				Una vez de haber ocultado el archivo se puede volver a aparecer y mostrar sus modificaciones y elimina el stash
git stash list				Muestra una lista de los archivos ocultos


GIT BRANCH
git branch				Muestra una lista de las branches en nuestro main repositorio
git branch <name_branch>		Crea una branch y se asigna un nombre al mismo
git checkout <name_branch>		Se cambia a la rama con el nombre
git checkout -b <name_branch>		Para cambiar a un nuebo branch <name_branch>

GIT TAG
Esta funcionalidad es para marcar puntos de liberación o de lanzamiento (v1.0.0, v2.0.0, etc.). Existen dos tipos de tags "lightweight" y "annotated".
git tag					Enlista los tags existentes
git tag -l "v#.#.#"			Busca un versión en especifico

GITHUB
git clone https://github.com/....git	Este comando clona un repositorio de github
git remote add origin <link>		Agrega nuestro repositorio local a un link en github
git push -u origin master		Cargará nuestro repositorio local a nuestro repositorio en github
git push				Cargará nuestro repositorio local a nuestro repositorio en github
git pull				Descargará las modificaciones que hayan sido subidas a nuestro repositorio en github
git remote -v				Muestra que nuestro proyecto agregado de github en el link correcto
git config user.name "some_name"	Para configurar el autor de las modificaciones
git config user.email "someone@mail.com"Para configurar el correo del autor de las modificaciones.



