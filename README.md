# Comandos de GIT

+ **git init** 						Inicializa un path en GIT
+ **git checkout**					Enlista los archivos modificados
+ **git status**					Comprueba el estado de los archivos dentro del repositorio.
+ **git add**						Agregamos el archivo a stagging area. (.) Agrega todos los archivos. O podemos agregar los archivos especificos que queramos escribiendolo continueamente ex. git add <filename1> <filename2. O podemos agregar los archivos especificos que queramos escribiendolo continueamente ex. git add <filename1> <filename2>
+ **git commit -m "message"**				Comando para generear un "checkpoint" un punto con log, un punto al cual se puede volver.
+ **git commit --amend**				Este comando es para actualizar el ultimo commit y evitar crear otro commit
+ **git commit --amend -m "message"**			Edita el ultimo commit con el nuevo mensaje
+ **git commit --amend --no-edit**			Si olvidamos agregar algun archivo a nuestro ultimo commit, nosotros podemos agregar un archivo al ultimo commit
+ **git commit -a -m "message"**				Este comando agrega todos los archivos modificados y crea un commit
+ **git diff <filename>**				Para revisar cuales son las diferencias del archivo con el ultimo commit
+ **git log**						Podemos ver todos los commits o "checkpoints" hechos del repositorio y un identificador SHA de cada commit
+ **git log --oneline**					Muestra los logs en una sola linea
+ **git log -n**					Limita el numero de log mostrasdos por commits, dependiendo el numero especificado
+ **git log --skip=*#***				Salta el numero de logs recientes. (No muestra los ultimos "n" logs)
+ **git log --author=*author***				Muestra los commits hechos por "author"
+ **git log --grep=*keyword***				Muestra los mensajes de los commits que contengan la palabra buscada
+ **git log --grep=*keyword* --invert-grep**		Muestra todos los resultados que NO contentan "keyword"
+ **git log --oneline --decorate --graph --all**	Genera una grafica con nuestros commits y merges
+ **git show HEAD**					Muestra el repositorio actual donde estamos trabajando y sus modificaciones
+ **git reset HEAD *filename***				Este comando es usado para quitar un archivo de la "staging area" o area de preparación para no ser crear un checkpoint en el commit con este archivo.
+ **git restore *filename***				Para restablecer un archivo eliminado del direcotrio de trabajo o descartar los cambios en el archivo
+ **git rm --cached *filename***			Elimina un archivo de nuestro repositorio local que es monitoreado de las modificaciones
+ **git checkout HEAD *filename***			Para restablecer un version mas vieja en el directorio de trabajo. La version mas vieja es la ultima en el git log y descarta los cambios hechos en stagging area
+ **git checkout --*filename***				Para restablecer un version mas vieja en el directorio de trabajo. La version mas vieja es la ultima en el git log y descarta los cambios hechos en stagging area
+ **git reset *commit_SHA***				Con este comando nosotos podemos regresar a un previo checkpoint con los primeros siete caracteres de un log. Lo que significa que estaremos borrando los checkpoints anteriores pero las modificaciones que se hicieron seguirian visibles en el archivo.

## GIT STASH
+ **git stash**						Se usa para almacenar en un repositorio oculto (como una pausa) se puede volver a el, esto oculta las ultimas modificaciones del archivo.
+ **git stash apply**					Muestra el archivo con las modificaciones ocultas pero no elimina el stash
+ **git stash drop**					Elimina el ultimo stash
+ **git stash drop stash@{#}**				Elimina un stash en especifico
+ **git stash clear**					Elimina todos los stashes
+ **git stash pop**					Una vez de haber ocultado el archivo se puede volver a aparecer y mostrar sus modificaciones y elimina el stash
+ **git stash list**					Muestra una lista de los archivos ocultos

## GIT BRANCH
+ **git branch**					Muestra una lista de las branches en nuestro main repositorio
+ **git branch <name_branch>**				Crea una branch y se asigna un nombre al mismo
+ **git branch -d *branch_name***			Borra un branch de mi repositorio local
+ **git checkout <name_branch>**			Se cambia a la rama con el nombre
+ **git switch *branch_name***				Cambia de branch
+ **git checkout -b <name_branch>**			Para cambiar a un nuevo branch <name_branch>
+ **git merge *branch_name***				Esto es para unir dos branches por ejemplo main y branch_name
+ **git rebase *branch_name***				Este comando es util cuando se han trabajado en dos branches y una de las branches se necesita poner por delante de la otra. Este comando traslada los commits que hace el rebase por delante de la otra branch. Es importante tener cuidado que branch hace el rebase. 


**git merge *branch_name***	
*Cuando uno intenta hacer merge en dos branches que ambas tuvieron modificaciones el merge entrara en conflicto (conflict). Esto se resuelve entrando al archivo y en el veremos las modificaciones marcadas con < ===== > que marcan el inicio, la division y el final de las modificaciones correspondientes a las dos branches. Aquí podemos decirdir quedarnos con una, con otra o incluso con las dos. Corremos de nuevo git add <filename>, esto mostrara el archivo en verde y una leyenda que los conflictos fueron resueltos y por ultimo un git commit -m "mensaje". De esta manera resolvemos un merging conflict.*

**git rebase *branch_name***	
*Cuando uno hace un rebase y se trabajó en el mismo archivo entrará en conflicto. El conflicto se resuelve de la misma forma en que se resuelve el conflicto en merge, decidiendo que linea entra, que linea sale, o si ambas se quedan. Esto es en cada commit hecho en el branch que entre en conflicto, así que probablemente se tenga que arreglar mas de un conflicto.*

Existe un metodo para combinar commits en un solo commit en un mismo branch. Se puede acceder a el desde **git rebase -i HEAD~#** esto abrira un vim editor de texto con el numero solicidado de commits. En el podremos ver el hash de cada commit y previamente a este hash una leyenda "pick" que sera reemplazada con "squash" y un solo "pick" y los commits se agruparan en ese unico pick, guardamos este archivo con *:wq*. Entonces se abrirá otro editor de texto con nuestras enmiendas de nuestros commits y poder editar el unico commit existente, *:wq*. Y así se finaliza este procedimiento.


## GIT TAG
Esta funcionalidad es para marcar puntos de liberación o de lanzamiento (v1.0.0, v2.0.0, etc.). Existen dos tipos de tags "lightweight" y "annotated". Crear tags es sumamente util cuando queremos volver a esa version de nuestro desarrollo y despues volver a la version mas reciente que se esta trabajando. Se pueden añadir tags en commits viejos.
+ **git tag**						Enlista los tags existentes
+ **git tag -l *v#.#.#***				Busca un versión en especifico
+ **git tag *v#.#.#>***					Creando un tag ligero
+ **git tag -a *v#.#.#* -m "message"**			Crea un annotated tag con la opción de agregar un mensaje en el tag
+ **git tag -a *v#.#.# checksum***			Este comando es para agregar un annotated tag in a specific commit point con su respectivo checksum number. Esto abrirá el editor de texto vi.
+ **git tag *new_tag old_tag_name***			Este comando es para poder renombrar un lightweight tag
+ **git tag -a *new_tag old_tag* ^{} -m "message"**	Este comando para poder renombrar un annotated tag y abrira el editor de texto vi para modificar el mensaje del tag previo
+ **git show *v#.#.#***					Muestra la información acerca del tag
+ **git checkout *v#.#.#***				Cambia a la version del tag
+ **git switch *branch_name***				Cambia al branch indicado y sale de la version
+ **git tag -d *v#.#.#***				Elimina un tag del repositorio local
+ **git push origin *tag***				Esto subira el tag especifico a nuestro repositorio de github
+ **git push --tags**					Esto subira todos los tags a nuestro repositorio de github
+ **git push origin --delete *v#.#.#***			Esto eliminara el tag especificado de nuestro repositorio de github


## GITHUB
+ **git clone https://github.com/....git**		Este comando clona un repositorio de github
+ **git remote add origin *link***			Agrega nuestro repositorio local a un link en github
+ **git push -u origin master**				Cargará nuestro repositorio local a nuestro repositorio en github
+ **git push**						Cargará nuestro repositorio local a nuestro repositorio en github
+ **git pull**						Descargará las modificaciones que hayan sido subidas a nuestro repositorio en github
+ **git remote -v**					Muestra que nuestro proyecto agregado de github en el link correcto (Origin o Remote; donde origin es nuestro repo en github y remote es el repositorio remoto de donde se hizo un fork, si se hizo un fork)
+ **git config user.name *some_name***			Para configurar el autor de las modificaciones
+ **git config user.email *someone@mail.com***		Para configurar el correo del autor de las modificaciones.
+ **git fetch *remote_branch***				Este comando solo buscará las modificaciiones hechas en una branch en github. Esto no mergeria.
+ **git push --set-upstream origin <branch_name>**		Esto crea la branch en github y sube el commit hecho en esa branch. (Para posteriormente hacer un Pull Request).

