# plantilla-taller
Este contenido es un fork del original de [Cristobal Contreras](https://github.com/lajaqueria/plantilla-taller) con algunas modificaciones. 

Esta es una plantilla para usar en los talleres de [Espacio Maker de Atigra](https://atigra.es), además de realizar algún documento de instrucciones y anotaciones. Está hecha con [MKDocs](https://www.mkdocs.org/) y usando el tema [Material Design](https://squidfunk.github.io/mkdocs-material/) (es muy completo y además se ve bien en móviles).

La plantilla ha sido diseñada por [Cristobal Contreras](https://github.com/crisconru) para usarla en sus talleres de [La jaquería](https://lajaqueria.org/).
Para la instalación y configuración en local he seguido la guía de [Federico Coca](https://fgcoca.github.io/Como-documento/), además de la guía de Cristobal, con lo cuál no duplicaré trabajo si no que, haré unas pequeñas anotaciones de como la he instalado yo en las nuevas versiones del sistema operativo linux (sistema basado en ubuntu 20.04 y 22.04 LTS) y python 3 (python 3.10).

La guía sigue el mismo esquema que la que tiene publicada [Cristobal](https://github.com/crisconru) en su Github. La licencia he dejado la misma que está publicada inicialmente, agradeciendo tanto a Cristobal como a Fede por los aportes ofrecidos por ellos.

## Pasos previos

1. Tienes que tener [Python 3](https://www.python.org/downloads/) instalado.
2. Tienes que instalar [PIP](https://pip.pypa.io/en/stable/installing/), el gestor de paquetes de Python.
3. * ~~Instalar [Pipenv](https://pipenv-es.readthedocs.io/es/latest/)~~ -> ~~`pip install pipenv`~~
   En mi caso no he instalado pipenv, si no que he utilizado el propio entorno virtual que viene integrado en las últimas versiones de python 3. En los siguientes pasos indicaré los comandos utilizados por mi. [Entornos virtuales y paquetes](https://docs.python.org/es/3/tutorial/venv.html)

Es altamente recomendado que uses un editor de texto tipo [Visual Studio Code](https://code.visualstudio.com/) / [Visual Studio Codium](https://vscodium.com/), [Atom](https://atom.io/), o similares para trabajar. Para esta plantilla se recomienda usar [VSCode](https://github.com/Microsoft/vscode/) o [VSCodium](https://github.com/VSCodium/vscodium) con las siguientes extensiones instaladas:

* [Markdown All in One](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one)
* [markdownlint](https://marketplace.visualstudio.com/items?itemName=DavidAnson.vscode-markdownlint)
* [TODO Highlight](https://marketplace.visualstudio.com/items?itemName=wayou.vscode-todo-highlight)
* [Todo Tree](https://marketplace.visualstudio.com/items?itemName=Gruntfuggly.todo-tree)

## Instalación

Esta plantilla está pensada para ser usada en un repositorio, aunque la puedes usar de manera local.
Cada uno de estos pasos viene más detallado en el documento creado por [Fede](https://fgcoca.github.io/Como-documento/).

1. Crea un repositorio en tu Github para tu taller.
2. A ese repositorio creale una rama que se llame `gh-pages`.
3. En la sección **Settings** de tu repositorio, vete la parte de **Github Pages** y habilita la opción de usar la rama **gh-pages**.
4. Descarga / clona tu repo en tu pc y recuerda que todo el rato vamos a trabajar en la rama `master`.
5. Descarga / clona esta plantilla, [plantilla-taller](https://github.com/LaJaqueria/plantilla-taller), en tu ordenador. En otro directorio que no sea donde estás trabajando. 
6. Copia de la rama `master` de `plantilla-taller` a la carpeta de tu taller:
      * Carpeta `docs`.
      * Fichero `mkdocs.yml`.
      * ~~Fichero `Pipfile` (el `Pipfile.lock` no).~~
      Si usas la alternativa de entorno virtual que he indicado antes **no es necesario copiar** este archivo Pipfile. 
      * Fichero `.gitignore` (si no lo ves activa los ficheros ocultos).
      * Fichero `LICENSE` (si no quieres que tu taller tenga licencia MIT, cambia su contenido, pero por favor, ponle licencia a tu taller).
      * Es **importante que** la carpeta `.git` **no la copies** bajo ningún concepto.
7. Abre una terminal en la carpeta de tu taller.
8. Crea el entorno virtual ejecutando:

```bash
      python3 -m venv venv
```

Instala las siguientes dependencias con el comando *pip* del siguiente modo.

```bash
      pip install wheel
      pip install mkdocs
      pip install click-man
      pip install mkdocs-material
      pip install mkdocs-minify-plugin
      pip install mkdocs-redirects

```
Tambien puedes instalar todas estas dependencias haciendo uso del archivo requirementsbasic.txt que se acompaña en este repositorio del siguiente modo:

```bash
      pip install -r requirementsbasic.txt
```

Ahora tendrás preparado tu equipo para poder trabajar con la plantilla.

## Como trabajar

### Montar taller en local

Para poder ver el taller en local como si estuviera en Internet, es necesario que levantes su servidor de pruebas. Es tan sencillo como desde la terminal en la carpeta de tu taller hagas

```bash
      mkdocs serve
```

Puede ser que al ejecutar el servidor os dé un error de ejecución con python, esto es debido (y estoy en investigación del motivo) al apartado 4. RSS del fichero mkdocs.yml, que no entiende el comando type, si comentamos todo este bloque conseguimos que funcione sin problemas.

Ahora en tu navegador podrás ver como va quedando tu taller en la web [http://127.0.0.1:8000/](http://127.0.0.1:8000/).

### Lista de tareas

Una vez abres el taller en la web, verás que en la página principal o home, tienes una lista de tareas. Esta página se corresponde al fichero `docs/index.html`. Ve siguiendo la lista de tareas y tendrás tu taller funcionando.

Como vereis son solo unas pocas modificaciones con respecto a la parte del entorno virtual de python, por lo demás todo sigue sin modificaciones.
