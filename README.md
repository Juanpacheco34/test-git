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
git branch
git branch -m "rama actual" "rama nueva"
git push origin --delete "rama a eliminar"

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
