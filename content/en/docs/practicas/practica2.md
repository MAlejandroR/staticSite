---
title: "Segunda tarea"
date: 2017-01-05
weight: 4
description: 
  
---

{{% pageinfo %}}
Introducción a Hugo. Primer sitio sencillo

{{% /pageinfo %}}

## Creación del sitio

``` bash
$ hugo new site primeros-pasos


Congratulations! Your new Hugo site is created in /home/lm/proyectos/cpilosenlaces/primeros-pasos.

Just a few more steps and you're ready to go:

1. Download a theme into the same-named folder.
   Choose a theme from https://themes.gohugo.io/ or
   create your own with the "hugo new theme <THEMENAME>" command.
2. Perhaps you want to add some content. You can add single files
   with "hugo new <SECTIONNAME>/<FILENAME>.<FORMAT>".
3. Start the built-in live server via "hugo server".

Visit https://gohugo.io/ for quickstart guide and full documentation.

```
Aquí vemos la información que se muestra tras crear el sitio web

Estructura creada:

``` bash
archetypes
config.toml
content
data
layouts
static
themes
```
Puedes ver el significado de los directorios en la [web de referencia de hugo] (https://gohugo.io/getting-started/directory-structure/): https://gohugo.io/getting-started/directory-structure/

## Instalar tema

Debes de seleccionar un tema según te interese

No debes de tener miedo en profundizar en un tema concreto. Todos funcionan de manera muy similar, si bien, de forma particular pueden terner requerimientos que seguro que en la web encuentras el guión de cómo proceder.

Ten encuenta que el tema que elijas va a ser la forma en la que vas a mostrar ***al mundo*** tu trabajol, así que selecciona el que más se ajuste a tus intenciones:

Ver los [temas de hugo](https://themes.gohugo.io/) : https://themes.gohugo.io/

> https://github.com/EmielH/tale-hugo

* Descargar a la carpeta themes. Renombrar la carpeta del tema a `tale`

* Modificar `config.toml`

  ```
   theme = "tale"
  ```

## Añadir contenido
(3 páginas)

``` hugo new contacto.md ```

## Añadir 3 posts
``` $ hugo new posts/esto-es-hugo.md ```

Editar markdown. Una imagen por post por lo menos.

### Añadir un menú

```toml
[menu]
  [[menu.main]]
	identifier = "contacto"
	name = "Contacto"
	title = "Contacto"
	url = "/contacto/"
	weight = 2
  [[menu.main]]
	identifier = "posts"
	name = "Posts"
	title = "Posts"
	url = "/posts/"
	weight = 3
  ```

## Publicar

  ```
  hugo 
  ```

## gh pages

  `hugo -d docs`

Modificar *config.toml*

  ```
  baseURL = "https://xxxxxxx.github.io/primeros-pasos"
  ```

* Crear un repositorio en GitHub
* Hacer el commit, para confirmar los cambios del sitio web en tu repositorio local
* Asociar el repositorio local con el repositorio remoto que has creado en Github
* Sincronizar el contenido del repositorio local hacia remoto
