# **_Git Test_**

_Aprendiendo comandos Git & GitHub con JonMircha_

## Comando Basicos:

```bash
git init
git --version
git config --global user.name "name"
git config --global user.email "email"
git --list

git remote add origin "url"
git remote -v

git pull
git add  "document name"
git add .
git commit
git commit -m ""
git push -u origin main
```

## Ramas

```bash
git branch
git branch -m "rama actual" "rama nueva"
git push origin --delete "rama a eliminar"

```

 -  Colocar por default esta rama en el remoto cuando se haga el siguiente push
``` bash
git symbolic-ref refs/remotes/origin/HEAD refs/remotes/origin/main
```
