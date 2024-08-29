# **_Git Test_**

_Aprendiendo Git & GitHub_

## Comando Basicos:

```bash
#Configuracion inicial
git init
git --version
git config --global user.name "nombre"
git config --global user.email "correo"
git --list

# Añadiendo repo a trabajar
git remote add origin "url"
git remote -v

# Actualizar en local a lo que tienes en remoto "TENER CUIDADO"
git pull

# Proceso para enviar tus datos del local al remoto
git add  "nombre del documento"
git add .
git commit
git commit -m "mensaje"

# Enviar cambios del local al remoto
git push -u origin "rama"
```

## Commit

```bash
# Ver los commit
git log   # informacion detallada del commit
git log --oneline  # informacion basica del commit
git log --oneline --graph --all # muestra los log con una grafica (es irrelevante)

#  Moverte a un commit en particular para revisar
# cuando termines de hacer eso regrasa a tu rama con el git checkout nombre de rama
git checkout "id del commit"
```

> > `Evitar usar estos comandos si ya enviaste al remoto ya que puede ocasionarte conflictos.`

```bash
#  Realizar nuevo commit sin editar el mensaje
git commit --amend --no-edit

# Ralizar cambio del commit solamente sin agregar cambios nuevos en los documentos trackeados
git commit --amend -m "nuevo commit"

# Ubicacion del los HEAD
git reflog

# Eliminar ultimo commit enviado al remoto para ver los cambios realizar push
# o al local si no lo has enviado al remoto 'TENER CUIDADO'
git reset --hard HEAD~1

```

## Ramas

```bash
# mostrar ramas
git branch

#crear y copiar todo
git branch -m "rama actual" "rama nueva"

# eliminar rama en remoto
git push origin --delete "rama a eliminar"

# crear
git branch "nombre de la rama"

# cambiar de rama
git checkout "nombre de la rama"

# crear y cambiarte a esa rama
git checkout -b "nombre de la rama"

# eliminar rama en local
git branch -d "nombre de la rama"

# forzar elimacion de rama
git branch -D "nombre de la rama"

# mostrar ramas no fusinadas a la actual
git branch --no-merged

# mostrar rams fusionadas a al actual
git branch --merged

# rebasar rama 'ESTUDIAR MAS EL TEMA'
git rebase "nombre de la rama que esta como principal"

# fusionar ramas 'Ubicarse a la rama que vas a copiar los datos y llamar a la que tiene los datos"
git merge "nombre de la rama"

```

> > `Colocar por default en el HEAD del remoto a esta rama x aunque es mas facil hacerlo en el propio github en setting`

```bash
git symbolic-ref refs/remotes/origin/HEAD refs/remotes/origin/"nombre de la rama"
```

## Remotos

```bash
# Mostrar nombre del remoto
git remote

# Añadir Remoto y Repositorio
git remote add origin/"or cualquier otro nombre" "url del github"

# Mostrar nombre del remoto y el repositorio al que estamos conectados
git remote -v

# Cambiar el nombre del remoto
git remote rename "nombre actual" "nombre nuevo"

# Eliminar el remote del local
git remote remove "nombre del remoto"

# Descargar rama que esta en el repositorio remoto
git checkout --track -b "nombre de la rama" origin"or nombre del remoto "/"nombre de la rama"
```

## .Gitignore

```bash

# esto es un comentario
archivo.ext
carpeta
/archivo_desde_raiz.ext

# ignorar todos los archivos que terminen en .log
*.log

# excepto production.log
!production.log

# ignorar los archivos terminados en .txt dentro de la carpeta doc,
# pero no en sus subcarpetas
doc/*.txt

# ignorar todos los archivos terminados en .txt dentro de la carpeta doc
# y también en sus subcarpetas
doc/**/*.txt
```

## Git Clone

```bash
git clone "url del repo"
```

## Guardar Commit

```bash
git log > commits.txt
```

## Historial

![Flujo de Git&GitHub](img/git-status.png)

> > **`Guiate con la imagen si tienes alguna duda`**

```bash
# Muestra si tenemos cambios para subir al remoto
git status

# Borra el HEAD en local
git reset --soft

# Borrar el staging que es despues del git add 'RECUERDA QUE ESTO ES SOLO EN LOCAL'
git reset --mixed
git restore --staged "nombre del archivo"

# Borran todo lo que crees despues del ultimo commit
#SI lo has guardado si no es asi no veras ninguna accion
git reset --hard

# Regresa a un commit en particular
#'TENER CUIDADA DESPUES DE HACER EL RESET NO HAY VUELTA ATRAS SI HAS HECHO PUSH'
git reset "id del commit"
git reset --hard "id del commmit"

```

## Etiquetas

> > `La usamos para versionar el proyecto en caso de que vaya escalando con el tiempo`

```bash
# Mostrar etiquetas creadas
git tag

# Mostrar informacion de la etiqueta
git show "numero de etiqueta or version"

# Crear etiquetas
git tag v1.0.0/"numero de etiqueta or version"

# Eliminar etiquetas
git tag -d "numero de etiqueta or version"


```
>> **`Proceso de Guardado Usar cual quiera de las dos dependiendo la necesida que tengas`**
``` bash
# Proceso 1: para guardar cambios en remoto para etiquetas 
git add .
git tag "numero de etiqueta or version"
git commit -m "numero de etiqueta or version"
git push origin "numero de etiqueta or version"


# Proceso 2: para guardar cambios en remoto para etiquetas.
git add .
git tag -a "numero de etiqueta or version" -m "mensaje del commit"
git push --tags

```
