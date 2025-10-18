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
