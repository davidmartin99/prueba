# Git Bash

## 1. Creamos un repositorio y lo iniciamos en Git Bash.
```plain
$ cd documents
$ mkdir practica_evaluable
$ cd practica_evaluable
$ git init
```
Hemos creado una carpeta llamada _practica_evaluable_ (**mkdir practica_evaluable**), y dentro de ella hemos inicializado un repositorio de git (**git init**).


## 2. Creamos y Validamos dos archivos.
```plain
$ echo "Este es mi Primer Documento">documento1.txt
$ echo "Este es mi Segundo Documento">documento2.txt
```
Tenemos ya dos archivos creados: _documento1.txt_ y _documento2.txt_ 

```plain
$ git status
$ git add .
$ git status
$ git commit -m "Los documentos 1 y 2 son válidos"
```
**git status** nos muestra el estado del repositorio, nos aparecerán los archivos en rojo, para ello los añadimos al área de preparación (**git add .**) y al ejecutar otra vez **git status** nos mostrará los archivos en verde.
Ahora tendremos que validarlo o commitearlo con **git commit -m "mensaje"**.


## 3. Realizar cambios en el primer documento.
```plain
$ nano documento1.txt
$ git add .
$ git commit -m ""
$ git diff
```
Con **nano documento1.txt** podremos editar el contenido del documento, luego con **git diff** podremos comprar el último commit (-), con el área del working (+).


## 4. Realizar cambios en el segundo documento y mostrar los commits.
```plain
$ nano documento2.txt
$ git add .
$ git commit -m ""
$ git log --oneline
```
Podremos mostrar en una sola línea los commits con **git log --oneline**


## 5. Revertir un commit.
```plain
$ git reset --hard <num_commit>
$ git log --oneline
```
Con **git reset --hard <num_commit>** volvemos a la situación de antes, es decir, nos situaremos en el commit que hayamos elegido.


## 6. Creamos un tercer documento.
```plain
$ echo "mensaje">documento3.txt
$ git add .
$ git commit -m ""
$ git log --oneline
```
Mismos pasos que anteriormente.


## 7. Revertir el último commit. 
```plain
$ git reset --hard <num_commit>
$ git log --oneline
```

## 8. Conectarse y subir cambios a un repositorio remoto.
```plain
$ git remote add origin <link_repositorio_remoto>
$ git push origin master
```
Nos conectamos a un repositorio remoto en GitHub llamado _practica_evaluable_. con **git remote add origin https://github.com/davidmartin99/practica_evaluable.git**
Luego subimos los cambios con **git push origin master**
> [!NOTE]
> La rama principal de un repositorio será **master** o **main**.

## 9. Creamos una rama.
```plain
$ git branch mirama
$ git branch
$ git checkout mirama
```
Nos creamos una rama **git branch mirama**, comprobamos qué ramas hay **git branch** y nos situamos en la rama creada **git checkout mirama**.
Añadiremos dos archivos _mirama1.txt_ y _mirama2.txt_ y los validaremos.
Mostraremos los commits.

## 10. Fusionar y borrar ramas.
```plain
$ git checkout master
$ git merge mirama master
$ git branch -d mirama
```
Fusionamos las ramas con **gir merge <rama_origen> <rama_destino>**.
Para borrar una rama ejecutamos **git branch -d <rama>**.


## 11. Sincronizamos con el repositorio remoto.
```plain
$ git push origin master
```
Con el comando **git push origin master** subiremos los cambios al repositorio remoto.

## 12. Crear una etiqueta con V1.
```plain
$ git tag V1
```
Usamos **git tag <nombre_etiqueta>**.

## 13. Clonar repositorios.
```plain
$ cd ..
$ mkdir practica_evaluable_2
$ cd practica_evaluable_2
$ git clone <url_repositorio_remoto>
```
A continuación clonaremos el repositorio remoto _practica_evaluable_ a un nuevo directorio local llamado _practica_evaluable_2_.
Primero ejecutamos **cd ..** para volver atrás y salir del repositorio local _practica_evaluable_, ahora creamos un repositorio **mkdir _practica_evaluable_2_** y nos situamos en él **cd practica_evaluable_2**;  clonamos el repositorio remoto **git clone <url_repositorio_remoto>**
También podemos ejecutar **git clone <url_repositorio_remoto> <nuevo_repositorio_local>**.


## 14. Creamos otra rama. 
```plain
$ git branch mirama
$ git checkout mirama
$ echo "mensaje" >>documento1.txt
$ git add .
$ git commit -m "mensaje"
$ git push origin mirama
```
Hemos creado una nueva rama con un archivo y la hemos subido al repositorio remoto.


## 15. Cambios en la rama master.
```plain
$ git checkout master
$ nano documento2.txt
$ git add .
$ git commit -m "mensaje"
$ git push origin master
```
Una vez hechos los cambios los subimos al repostiorio remoto.


## 16. Realizar un merge entre dos ramas.
```plain
$ git merge mirama master
$ git branch -d mirama
$ git push origin master
$ git log --oneline
```

## 17. Cambios en el documento2.txt
```plain
$ echo “Nuevo comentario”>>documento2.txt
```
Añadimos una línea al _documento2.txt_


## 18. Creamos una nueva rama y realizamos cambios diferentes que en el punto anterior.
```plain
$ git branch mirama
$ git checkout mirama
$ echo “Dentro de mirama”>>documento2.txt
```

## 19. Conflicto al fusionar dos ramas.
```plain
$ git merge mirama master
$ nano documento2.txt
$ cat documento2.txt
$ git add .
$ git commit -m "Resolver conflicto fusión"
```
Al intentar fusionar dos ramas con dos archivos iguales pero con diferente contenido, surgirá un conflicto:
> [!CAUTION]
> Auto-merging documento2.txt
> CONFLICT (content): Merge conflict in documento2.txt
> Automatic merge failed; fix conflicts and then commit the result.

 Abriremos el archivo y lo editaremos con los cambios que queremos guardar; por último lo validamos.
 


> [!TIP]
> - "<<<<<<<" HEAD es donde estamos situados ahora.
> - "=======" divide las diferencias entre las dos ramas.
> - ">>>>>>>" cierre de diferencias.

## 20. Sincronizamos con el repositorio remoto. 
```plain
$ git push origin master
```

