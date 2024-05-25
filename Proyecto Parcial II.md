## Creación de repositorio

Para este paso primero debemos inicializar el repositorio con el comando ```git init```, o clonar un repositorio existente con el comando ```git clone```. Para este caso en particular utilizaré git clone porque ya había creado el repositorio.

`Cloning into 'pp2'...`
`warning: You appear to have cloned an empty repository.`
`rodorio@rodorio:~/Documents$ cd pp2`
`rodorio@rodorio:~/Documents/pp2$` 

## Añadir archivos al repositorio

Por el momento tengo el repositorio vacío. Para agregar este documento al repositorio, utilizaré el comando ```git add``` seguido con el comando ``` git commit -m```. Commit va a guardar los cambios hechos hasta el momento, en este caso la creación del README y la bandera -m es para indicar los cambios que hice.

```git commit -m "added README"
[main (root-commit) b92f09f] added README
 1 file changed, 9 insertions(+)
 create mode 100644 README.md
 ```
 
Por ahora los cambios están solo en mi carpeta local. Para poder hacer los cambios en el repositorio de github tengo que usar el comando ```git push origin```. Ya que por el momento no tengo ninguna rama creada este comando basta para publicar los cambios.

```rodorio@rodorio:~/Documents/pp2$ git push origin
Username for 'https://github.com': mightysarcasm
Password for 'https://mightysarcasm@github.com': 
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Delta compression using up to 4 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 468 bytes | 468.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
To https://github.com/mightysarcasm/pp2.git
 * [new branch]      main -> main

```

Puedo crear y eliminar archivos de esta misma forma.
Crearé un archivo llamado "paralabasura" y lo eliminare posteriormente.

```rodorio@rodorio:~/Documents/pp2$ touch paralabasura.txt
rodorio@rodorio:~/Documents/pp2$ git add paralabasura.txt
rodorio@rodorio:~/Documents/pp2$ git commit 
[main b37d5b8] agregar archivo para borrar
 1 file changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 paralabasura.txt
rodorio@rodorio:~/Documents/pp2$ git push origin
Username for 'https://github.com': mightysarcasm
Password for 'https://mightysarcasm@github.com': 
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 4 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 297 bytes | 297.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
To https://github.com/mightysarcasm/pp2.git
   b92f09f..b37d5b8  main -> main

```

Aquí se creo el archivo que eliminaré posteriormente. En este caso no utilicé la bandera -m en el commit, lo que hace que se abra el editor de texto de la terminal para escribir ahi la descripción del commit.

```
rodorio@rodorio:~/Documents/pp2$ git rm paralabasura.txt
rm 'paralabasura.txt'
rodorio@rodorio:~/Documents/pp2$ git commit -m "remove text file"
[main 578603d] remove text file
 1 file changed, 0 insertions(+), 0 deletions(-)
 delete mode 100644 paralabasura.txt
rodorio@rodorio:~/Documents/pp2$ git push origin
Username for 'https://github.com': mightysarcasm
Password for 'https://mightysarcasm@github.com': 
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Delta compression using up to 4 threads
Compressing objects: 100% (1/1), done.
Writing objects: 100% (2/2), 241 bytes | 241.00 KiB/s, done.
Total 2 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
To https://github.com/mightysarcasm/pp2.git
   b37d5b8..578603d  main -> main

```

Con el comando ``rm`` voy a eliminar el archivo que yo indique.

## Comandos adicionales y variaciones

### `git remote`

Gestiona las conexiones con repositorios remotos.

- `git remote add origin https://...`: Agrega un nuevo repositorio remoto.
- `git remote -v`: Muestra las URL de los repositorios remotos configurados.
```rodorio@rodorio:~/Documents/pp2$ git remote -v
origin	https://github.com/mightysarcasm/pp2.git (fetch)
origin	https://github.com/mightysarcasm/pp2.git (push)

```

### `git add`

- `git add .`: Agrega todos los archivos que estén en mi directorio.

### `git rm`


- `git rm -r directorio/`: Elimina un directorio completo del repositorio.

### `git pull`

Descarga los cambios del repositorio  y los fusiona con el repositorio local.

```git purodorio@rodorio:~/Documents/pp2$ git pull origin
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (3/3), 946 bytes | 473.00 KiB/s, done.
From https://github.com/mightysarcasm/pp2
   74f13d2..db4744c  main       -> origin/main
Updating 74f13d2..db4744c
Fast-forward
 gitpull.txt | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 gitpull.txt

```

Creé un archivo llamado gitpull.txt directamente en github y con git pull lo copie a mi repositorio local.
### `git checkout`

Con este comando puedo hacer cambios hacia otras ramas o commits previos.

```git log
commit db4744c0fb871e8d1790bdeeb3b7cb1494fd5312 (HEAD -> main, origin/main)
Author: mightysarcasm <103285938+mightysarcasm@users.noreply.github.com>
Date:   Fri May 24 22:44:05 2024 -0600

    Create gitpull.txt

commit 74f13d240df1aaa11bcac95a27428607d03950f9
Author: mightysarcasm <rafagav@protonmail.com>
Date:   Fri May 24 22:31:27 2024 -0600

    Update Readme

commit 578603d0bd8665505774dd6c7cfceb98b218b0b5
Author: mightysarcasm <rafagav@protonmail.com>
Date:   Fri May 24 21:59:00 2024 -0600

    remove text file

commit b37d5b89fc19a72ffcb789171385e43a771dca91
Author: mightysarcasm <rafagav@protonmail.com>
Date:   Fri May 24 21:54:49 2024 -0600

    agregar archivo para borrar
:


```


Con git log puedo ver la lista de mis commits con sus respectivos hashes, y con checkout puedo revertir el proyecto a un commit anterior. EN este caso antes de hacer la prueba de git pull.

```it checkout 74f13d240df1aaa11bcac95a27428607d03950f9
Note: switching to '74f13d240df1aaa11bcac95a27428607d03950f9'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at 74f13d2 Update Readme
rodorio@rodorio:~/Documents/pp2$ 


```



### `git branch`

Gestiona las ramas del repositorio.

- `git branch`: Muestra las ramas existentes y la rama actual.
```rodorio@rodorio:~/Documents/pp2$ git branch
* (HEAD detached at 74f13d2)
  main

```

Para crear una rama nueva puedo utilizar el comando:

```
rodorio@rodorio:~/Documents/pp2$ git branch newBranch
rodorio@rodorio:~/Documents/pp2$ git branch
* (HEAD detached at 74f13d2)
  main
  newBranch

```
### `git reset`

Deshace commits que se encuentren en el staging area.

### `git revert`

Crea un nuevo commit que deshace los cambios hechos en un commit anterior.

- `git revert commit-hash`: Crea un nuevo commit que deshace los cambios del commit que le indique.


### `git log`

Muestra el historial de commits.

- `git log --oneline`: Muestra el historial pero en una versión mas compacta

```
rodorio@rodorio:~/Documents/pp2$ git log --oneline
74f13d2 (HEAD, newBranch) Update Readme
578603d remove text file
b37d5b8 agregar archivo para borrar
b92f09f added README

```

### `git squash`

Sirve para combinar varios commits en uno solo.