---
title: "Cómo añadir contenido"
date: 2021-10-04T13:19:24+02:00
draft: false
weight: 2
---
{{% pageinfo %}}
**Objetivo**: 
* Estructurar contenido para mejorar la visualización del sitio.
* Organizar los contenidos que vamos a publicar (Orgnaizaremos por directorios y ficheros)

**Documentación:**
* https://gohugo.io/content-management/organization/ 
* https://desarrolloweb.com/articulos/generar-contenido-site-hugo
{{% /pageinfo %}}






## ¿Qué estructura tiene el contenido de las páginas?
* Tipos de páginas de contenido. Agrupar las páginas por tipos.
* En Hugo el contenido se organiza como luego se va a ver en la web. Anidamos el contenido en subdirectorios (**secciones**): `content/<directorios>`
* Pensar en **front-matter** - **archetypes**
* Plantillas específicas para cada modelo

## Creando contenido
Para crear nuevo contenido vamos  a generar páginas de texto con formato **markdown** [*(Hablamos más abajo sobre el tema)*](#markdown)

Usarmeos el CLI de hugo (linea de comandos) para crear ficheros de contenido y/o secciones
```bash
hugo new [seccion]/fichero.md
```
La sección puede ser un directorio o varios (subdirectorios anidados)

Los ficheros se crean en la carpeta **content** del directorio raíz del proyecto

El fichero creado tendrá un  contenido según quede especificado en el fichero **patrón** ubicado en la carpeta **archetypes/default.md**
{{% pageinfo%}}
 **Creando un fichero md**
```bash
hugo new docs/prueba.md
```
*Genera un fichero con el siguiente contenido*
```toml
---
title: "Prueba"
date: 2021-10-04T19:39:33+02:00
draft: false
---


```
{{%/pageinfo%}}
**Las páginas en el directorio content**
*Las páginas ubicadas directamente en el directorio **content** serían páginas que podríamos decir globales o bundles pages: contacto, about, datos relevantes, ....

*Las páginas que se organizan en una sección concreta serán páginas relacionadas con el tema de la sección: teoría, prácticas ,....

*Por otro lado, cada directorio puede contener un fichero llamado **_index.md** que va a contener el índice o información que se visualizará al cargar la sección concreta, sería como el fichero índice de sección .

### Front   matter
 https://gohugo.io/content-management/front-matter/

Los ficheros de contenido pueden tener ***metainformación*** en la cabecera o inicio del fichero
Esta información va entre tres líneas y constituye lo que se llama el **front matter** de la página
En esta sección daremos valores a variables que luego se pueden utilizar

La información del fichero creado anteriormente corresponde al **Front matter**





## Secciones
Se pueden anidar todas las secciones que sean necesarias.

Cada directorio en **content**  *hugo* lo ve como una sección
También vamos a considerar secciones esos directorios que contengan  un fichero **_index.md**

```
content
└── blog        <-- Sección, porque es el primer nivel bajo content/  
    |   ├── funny-cats
    │   ├── mypost.md
    │   └── kittens         <-- Sección porque contiene _index.md
    │       └── _index.md
    └── tech                <-- Sección porque contiene _index.md
        └── _index.md

```

Por defecto Hugo asume que las páginas pertenecen al **Content Type** de la sección inicial, es decir que `posts/post-1.md` es de tipo `posts`. Si existe un **archetype** para la  sección **posts**, hugo generará un **frontmatter** específico. Ver [archetypes](https://gohugo.io/content-management/archetypes/)


## Páginas `_index.md`

* Añaden **front-matter** y contenido a las **list templates**
* La función `.Site.GetPage` da acceso a contenido y metadatos.


```
          url
        ⊢  ^ ⊣
        path    slug
        ⊢--^-⊣⊢---^---⊣
           filepath
        ⊢------^------⊣
content/posts/_index.md
```

Ejemplo de **list.html** 

```go-html-template
{{ define "main" }}
    <h2>{{ .Title }}</h2>
    <ul>
    {{ range .Pages }}
        <li><a href=​ "{{ .RelPermalink }}"​ >{{ .Title }}</a></li>
    {{ end }}
    </ul>
{{ end }}
```


## Páginas normales en secciones

* Se muestran conlas **single page templates**

## Explicación de las rutas

* filename
* slug
* section
* type
* url


Se pueden modificar en el **frontmatter**: `slug, type y url`

## Front Matter

* Lo que precede al contenido
* Sintaxis especial
* Hay unas variables predefinidas pero el usuario puede crear nuevas.
* Se genera según el **archetype** de la sección. Por defecto *_default.md*
* Se pueden pasar valores por defecto a las páginas que descienden de una sección.

Por ejemplo si ponemos en `content/blog/_index.md`
```toml 
title = 'Blog'
[cascade]
  banner = 'images/typewriter.jpg'
```
Esta página y todas las que descienden de la sección `blog` devuelven `images/typewriter.jpg` en `.Params.banner` a no ser que tengan su propio banner o un ancestro más cercano lo modifique.


### Documentación relacionada:
* https://gohugo.io/content-management/front-matter/
* https://gohugo.io/variables/page/

## Taxonomías
https://gohugo.io/content-management/taxonomies

Una taxonomía es una categorización que nos permite clasificar contenido.

Por ejemplo, en una web de Películas podríamos tener actores, directores, estudios, géneros, años, premios ... 

Por defecto Hugo añade las taxonomías **categories** y **tags**. Se pueden añadir más en **config**

```toml
[taxonomies]
  category = 'categories'
  tag = 'tags'
```
Si se quiere deshabilitar:

```toml
disableKinds = ['taxonomy', 'term']
```

En **frontmatter**
```yaml
categories:
- Personal
- Trabajo
tags:
- software
- html
```

## Markdown

Repaso (o apredner) la sintaxis:

* [https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet)
* https://programminghistorian.org/es/lecciones/introduccion-a-markdown
* 
Este metalenguaje o lenguaje con marcas es muy utilizado en la  documentación técnica.

Es importante aprender a utilizarla con cierta flexibilidad

