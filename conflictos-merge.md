# Resolución de conflictos al hacer merge

Al momento de realizar el punto 4 de la siguiente manera:

```bash
git merge proyectos
```

Obtuve la siguiente salida:

```bash
Auto-merging README.md
CONFLICT (content): Merge conflict in README.md
Automatic merge failed; fix conflicts and then commit the result.
```

Al abrir el archivo `README.md` con Visual Studio Code encontré que dentro del mismo había unas marcas:

```
<<<<<<< HEAD
## Anotación: de qué se trata el curso

El curso **GIT y herramientas para implementar el control de versiones en aplicaciones para desarrolladores/as** intenta dar un vistazo de `qué es Git` (_control de versionado de software_). `Github y Gitlab` (_Creación de repositorios desde Github y Gitlab -crear, inicializar, asociar o clonar un repositorio.-_). `Ramas o branches` (_manejo de ramas para trabajo en simultáneo_).

## Herraminetas para aprender ramas en Git

### 1. Learn Git Branching

**Descripción:**
Learn Git Branching es una herramienta interactiva que proporciona un entorno visual para aprender los conceptos de Git, especialmente el manejo de ramas. Ofrece una serie de tutoriales y desafíos que te guían a través de las operaciones comunes de Git, como crear, fusionar y rebase de ramas. Su interfaz gráfica ayuda a visualizar cómo las ramas y los commits se relacionan entre sí, lo que facilita la comprensión de estos conceptos.

**Características destacadas:**

- Entorno interactivo con visualizaciones en tiempo real.
- Lecciones paso a paso desde conceptos básicos hasta avanzados.
- Desafíos prácticos para poner a prueba tus conocimientos.
- Disponible en varios idiomas.

**Link:**
[Learn Git Branching](https://learngitbranching.js.org/)

### 2. GitKraken Git Tutorial

**Descripción:**
GitKraken Git Tutorial ofrece una serie de tutoriales detallados sobre Git, incluyendo el manejo de ramas. Los tutoriales están diseñados para ser fáciles de seguir y proporcionan ejemplos prácticos que puedes probar en tu propio entorno. GitKraken también ofrece un cliente Git visual que puede facilitar la gestión de ramas y otras operaciones de Git.

**Características destacadas:**

- Tutoriales claros y detallados sobre varios aspectos de Git.
- Ejemplos prácticos que puedes seguir paso a paso.
- Recursos adicionales para profundizar en el aprendizaje.
- Integración con el cliente GitKraken para una experiencia visual y práctica.

**Link:**
[GitKraken Git Tutorial](https://www.gitkraken.com/learn/git/tutorials)
=======
## Poncho

Base de html y css para la creación de sitios pertenecientes a la Administración Pública Nacional de la República Argentina.

En este repositorio podés descargar los archivos de Poncho para trabajar de manera local.
Esta nueva versión de Poncho incluye cambios de colores y otros elementos que mejoran cuestiones de accesibilidad.

Para usar Poncho en un sitio, ver [la documentación](http://argob.github.io/poncho).
También estamos en [NPM](https://www.npmjs.com/package/ar-poncho).
>>>>>>> proyectos
```

## Resolución

Según pude ver, lo que está al principio (entre `<<<<<<< HEAD` y `=======`) corresponde a todos los commits que hice sobre la rama principal, mientras que lo que está al final (entre `=======` y `>>>>>>> proyectos`) corresponde a los commits que hice sobre la rama `proyectos`.

Para resolver el conflicto decido incluir **todos los cambios** del archivo `README.md` dejándolo tal como está ahora en la rama principal.

Acto seguido, debo volver a agregar el archivo y la carpeta que no existía en esta rama (`git add .`) y puedo hacer el commit correspondiente al punto 4.
