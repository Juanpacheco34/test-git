# **_Git Test_**

_Aprendiendo comandos Git & GitHub con JonMircha_

## Comando Basicos:

```bash
git init
git --version
git config --global user.name "nombre"
git config --global user.email "correo"
git --list

git remote add origin "url"
git remote -v

git pull
git add  "nombre del documento"
git add .
git commit
git commit -m "mensaje"
git push -u origin "rama"
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

# rebasar rama
git rebase "nombre de la rama que estac como principal"

```

 -  `Colocar por default en el HEAD del local a esta rama x`
``` bash
git symbolic-ref refs/remotes/origin/HEAD refs/remotes/origin/"nombre de la rama"
```

## .Gitignore
``` bash 

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

# ignorar todos los archivos terminados en .txt dentro de la carpeta doc y también en sus subcarpetas
doc/**/*.txt
```

## Git Clone
``` bash
git clone "url del repo" 
```
