# Automatización de GitHub con Python

Este proyecto incluye un **script en Python (`prueba.py`)** que permite automatizar tareas básicas en un repositorio de GitHub, usando la librería [PyGithub](https://pygithub.readthedocs.io/).

## Funcionalidades
- Crear **issues automáticamente** en un repositorio especificado.
- Permite definir **título y descripción** de cada issue desde una lista en Python.
- Puede ampliarse fácilmente para leer datos desde **CSV/JSON** o generar contenido con IA.

## Requisitos
- Python 3.10+
- Librería PyGithub:
    pip install PyGithub
- **Token personal de GitHub** con permisos:
    - `public_repo` si el repo es público
    - `repo` si el repo es privado

## Uso
1. Editar `prueba.py` con tu token y el nombre del repositorio (`usuario/repositorio`).
2. Modificar la lista `issues` con los títulos y descripciones que quieras crear.
3. Ejecutar el script:
    python prueba.py
4. Verás en consola la confirmación de cada issue creada y aparecerán en tu repositorio de GitHub.
# Actualización automática del README desde local

Este proyecto incluye un **script en Python (`updateReadme.py`)** que permite actualizar automáticamente el README de tu repositorio de GitHub usando el contenido de tu README local.

## Funcionalidades
- Leer el contenido de `README.md` local y subirlo al repositorio remoto.
- Evita tener que usar `git add .` y `git commit -m "..."` cada vez que cambias el README.
- Hace commit automático con mensaje personalizado.

## Requisitos
- Python 3.10+
- Librería PyGithub:
    pip install PyGithub
- **Token personal de GitHub** con permisos:
    - `public_repo` si el repo es público
    - `repo` si el repo es privado

## Uso
1. Editar `updateReadme.py` con tu token y el nombre del repositorio (`usuario/repositorio`).
2. Modificar tu README local (`README.md`) como desees.
3. Ejecutar el script:
    python updateReadme.py
4. Verás en consola la confirmación:
    "README actualizado correctamente en GitHub ✅"



# Automatización de la actualización del README con Python

Este script (`updateReadme.py`) permite actualizar automáticamente el README de un repositorio de GitHub usando el contenido de un README local, sin necesidad de usar Git manualmente.

## Cómo funciona

### 1. Leer contenido local
with open(ruta_local, "r", encoding="utf-8") as f:
    nuevo_contenido = f.read()

- `ruta_local` es la ruta del README local (por ejemplo "README.md").  
- `open(..., "r", encoding="utf-8")` abre el archivo en modo lectura con codificación UTF-8.  
- `with ... as f:` asegura que el archivo se cierre automáticamente al terminar.  
- `f.read()` lee todo el contenido del archivo y lo guarda en `nuevo_contenido`.  

### 2. Actualizar README en GitHub
repo.update_file(
    path="README.md",
    message="Actualización automática del README",
    content=nuevo_contenido,
    sha=file.sha
)

- `repo.update_file()` sobrescribe un archivo en el repo remoto.  
- Parámetros:
  - `path="README.md"` → ruta del archivo en GitHub.
  - `message="..."` → mensaje del commit que aparecerá en GitHub.
  - `content=nuevo_contenido` → el nuevo contenido que quieres subir.
  - `sha=file.sha` → SHA de la versión actual del archivo remoto, necesario para que GitHub sepa qué versión se está actualizando.
- Esto genera un commit automático:
  - El mensaje del commit es el que pasaste en `message`.
  - El autor del commit es el usuario asociado al token.
  - El commit incluye solo los cambios en el README, sin afectar otros archivos.
- SHA: cada commit recibe un SHA único; el SHA pasado como parámetro identifica la versión del archivo que se está actualizando y asegura que no se sobrescriban cambios de otros commits.  

### Resumen
1. Se lee el README local y se guarda en `nuevo_contenido`.
2. `update_file()` sube automáticamente este contenido al repo remoto.
3. GitHub crea un commit con el mensaje especificado, usando el usuario del token.
4. No necesitas usar `git add`, `git commit` ni `git push` manualmente.


hola nueva actualización


hola nuevoa sdlkfjasldfp aospdif ask