# **Git Test**

_Aprendiendo Git & GitHub_

## Comandos básicos:

```bash
# Configuración inicial
git init
git --version
git config --global user.name "nombre"
git config --global user.email "correo"
git config --list

# Añadir repositorio remoto
git remote add origin "url"
git remote -v

# Sincronizar con la rama remota (CUIDADO)
git pull origin "rama"

# Preparar cambios para enviar
git add "nombre_del_documento"
git add .
git commit -m "mensaje del commit"

# Enviar cambios al repositorio remoto
git push -u origin "rama"
```

## Commits

```bash
# Ver historial de commits
git log                     # Detallado
git log --oneline           # Básico
git log --oneline --graph --all  # Con visualización gráfica

# Moverse a un commit específico (modo lectura)
git checkout "ID_del_commit"

# Regresar a tu rama después de revisar
git checkout nombre_rama
```


```bash
# Editar el último commit sin cambiar mensaje
git commit --amend --no-edit

# Cambiar mensaje del último commit
git commit --amend -m "nuevo mensaje"

# Ver historial de HEAD
git reflog

# Eliminar último commit
git reset --hard HEAD~1
```

## Ramas

```bash
# Ver ramas disponibles
git branch

# Crear rama
git branch nombre_rama

# Cambiar de rama
git checkout nombre_rama

# Crear y cambiar a una rama
git checkout -b nombre_rama

# Eliminar rama local
git branch -d nombre_rama

# Forzar eliminación
git branch -D nombre_rama

# Eliminar rama remota
git push origin --delete nombre_rama

# Renombrar rama actual
git branch -m nuevo_nombre

# Ramas fusionadas / no fusionadas
git branch --merged
git branch --no-merged

# Rebase (estudiar bien antes de usar)
git rebase rama_base

# Fusionar ramas
git merge nombre_de_la_rama
```

> ⚙️ **Establecer rama por defecto (también se puede hacer en GitHub Settings):**

```bash
git symbolic-ref refs/remotes/origin/HEAD refs/remotes/origin/nombre_rama
```

## Remotos

```bash
# Ver remotos configurados
git remote

# Añadir remoto
git remote add origin "url"

# Ver remotos con detalle
git remote -v

# Renombrar remoto
git remote rename nombre_actual nombre_nuevo

# Eliminar remoto
git remote remove nombre

# Descargar y rastrear una rama remota
git checkout --track -b nombre_rama origin/nombre_rama
```

## `.gitignore`

```gitignore
# Comentarios
archivo.ext
carpeta/
archivo_desde_raiz.ext

# Ignorar por extensión
*.log

# Excepciones
!production.log

# Ignorar solo en una carpeta
doc/*.txt

# Ignorar también subcarpetas
doc/**/*.txt
```

## Clonar un repositorio

```bash
git clone "url"
```

## Guardar historial de commits en un archivo

```bash
git log > commits.txt
```

## Historial de estado

![Flujo de Git & GitHub](img/git-status.png)

> **Guíate con la imagen si tienes dudas**

```bash
# Ver estado actual
git status

# Borrar solo el HEAD local
git reset --soft

# Borrar el staging (post `add`)
git reset --mixed
git restore --staged nombre_archivo

# Borrar cambios no confirmados
git reset --hard

# Volver a commit anterior
git reset ID_commit
git reset --hard ID_commit
```

## Etiquetas

> 📌 Usadas para versionar proyectos

```bash
# Ver etiquetas
git tag

# Ver detalle de una etiqueta
git show v1.0.0

# Crear etiqueta simple
git tag v1.0.0

# Eliminar etiqueta
git tag -d v1.0.0
```

### Guardar etiquetas en remoto

```bash
# Método 1
git add .
git tag v1.0.0
git commit -m "Versión 1.0.0"
git push origin v1.0.0

# Método 2 (anotada)
git add .
git tag -a v1.0.0 -m "Versión 1.0.0"
git push --tags
```

---

### 📚 [Aprende más a fondo sobre Git & GitHub con Jon Mircha](https://www.youtube.com/watch?v=suzMNqDQiyU)
