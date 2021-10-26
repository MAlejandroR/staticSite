# Objetivo

Este es un sitio web que se usa para explicar el uso de hugo en el módulo de Desarrollo web del CPI Los enlaces

En este caso se usa el tema de [docsy](https://www.docsy.dev/docs/)

Abajo se expone como se puede instalar este sitio
Se puede ver en github page o desplegado en un servidor con vesta:

* https://malejandror.githuab.io/staticSite
* http://manuel.infenlaces.com/dwes/hugo

# Instalarlo en local para desarrollo

1. descargar el proyecto
```bash
git clone https://github.com/MAlejandroR/staticSite
```

2. ir a la carpeta creada
```bash
cd staticSite
```

3. Instalar el thema docsy bajo la carpeta themes/docsy

```bash
  cd themes
  git clone https://github.com/google/docsy.git docsy  
```

4. Actualizar los links que usa docsy e instalar postcss

  Postcss se usa para transpilar de sass a css, por ello si no lo tienes instalado, hay que instalarlo en el sistema

```bash
  sudo npm install -D autoprefixer
  sudo npm install -D postcss-cli
  sudo npm install -D postcss
```
Ahora debemos actualizar el repositorio de docsy para que funcione en local.
docsy usa sus propios módulos los cuales tenemos que descargar y actualizar
Para ello nos ubicamos dentro de la carpeta docsy y ahí ejeccutamos un comando git de actualizar módulos

```bash
  cd $HOME/staticSite/themes/docsy/
  git submodule update --init --recursive --depth 1

```

5. Levantar el servidor

Con el comando CLI de hugo, podemos levantar el servidor en local

Para ello, ubicado en la carpeta del proyecto $HOME/staticSite levantamos un servidor local
El & lo uso en linux para dejar la tarea en background y seguir teniendo disponible el terminal (si no quedaría bloqueado por el proceso que acabaría de lanzar)

```bash
 hugo server &
```


 