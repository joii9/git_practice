Comandos de GIT

git init		Inicializa un path en GIT
git status			Comprueba el estado de los archivos dentro del repositorio
git add				Agregamos el archivo a stagging area. (.) Agrega todos los archivos. O podemos agregar los archivos especificos que queramos escribiendolo continueamente ex. git add <filename1> <filename2. O podemos agregar los archivos especificos que queramos escribiendolo continueamente ex. git add <filename1> <filename2>
git diff <filename>		Para revisar cuales son las diferencias del archivo con el ultimo commit
git commit -m "message"		Comando para generear un "checkpoint" un punto con log, un punto al cual se puede volver.
git log				Podemos ver todos los commits o "checkpoints" hechos del repositorio y un identificador SHA de cada commit
git checkout HEAD <filename>	Para restablecer un version mas vieja en el directorio de trabajo. La version mas vieja es la ultima en el git log y descarta los cambios hechos en stagging area
git show HEAD			Muestra el repositorio actual donde estamos trabajando y sus modificaciones
git reset HEAD <filename>	Este comando es usado para quitar un archivo de la "staging area" o area de preparación para no ser crear un checkpoint en el commit con este archivo.
git checkout --<filename>	The same than line upper
git reset <commit_SHA>		Con este comando nosotos podemos regresar a un previo checkpoint con los primeros siete caracteres de un log. Lo que significa que estaremos borrando los checkpoints anteriores pero las modificaciones que se hicieron seguirian visibles en el archivo.
git restore <filename>		Para restablecer un archivo eliminado del direcotrio de trabajo o descartar los cambios en el archivo


