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