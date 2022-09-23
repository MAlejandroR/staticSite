---
title: "Instalación"
date: 2021-10-04T12:01:52+02:00
draft: false
weight: 1
description: >
    Instalación e inicio de herramientas para el desarrollo y configuración 

---

***
## Sección de pruebas

***

## Instalación 

Tiene instaladores para mac, windows y linux:
* [https://gohugo.io/getting-started/quick-start/#step-1-install-hugo](https://gohugo.io/getting-started/quick-start/#step-1-install-hugo)


{{% pageinfo %}}
Recuerda:
* Instalar la herramienta hugo
* Configurar el **path** del sistema para acceder desde cualquier invocación
* Gestionamos desde un terminal todo
* Verifica la versión 
{{% /pageinfo %}}

{{< tabpane >}}
{{< tab header="apt-get" lang="shell">}}
    sudo apt-get install hugo
  {{< /tab >}}
  {{< tab header="snap" lang="shell">}}
    sudo snap install hugo --classic
  {{< /tab >}}
{{< /tabpane >}}
Si no tuviera [snap](https://snapcraft.io/docs/snap-documentation) instalado
```bash
sudo apt-get install snapd
```

{{% pageinfo %}}
*Mejor instalamos con **snap** para obtener la versión última
{{% /pageinfo %}}

Esta opción actualmente instala una versión 0.68 ***La actual es 0.88***

Otra opción es instalar con  snap , o bien descargar el paquete de la web  [Página de hugo](https://gohugo.io)

## Editor para el desarrollo

Interesante usar Visual Code.
```bash
sudo snap install code --classic
```

Una vez instalado si escriben en el terminal ***code .*** te habre el editor y te carga el directorio actual

* Puedes abrir el terminal desde el entorno
* Puedes commitear desde el editor y subir a git *Esto ya lo veremos más adelante*
* Instalar muchos plugins según necesidades

## Crear un sitio nuevo
Mejor tener una carpeta concreta para los sitios que vayamos a crear

{{<highlight javascript >}}
$ hugo new site <nombre_del_sitio>
{{</highlight>}}

{{% alert title="Warning" color="warning" %}}
This is a warning.
{{% /alert %}}

## Configuración 
