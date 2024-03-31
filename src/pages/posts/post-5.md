---
layout: ../../layouts/MarkdownPostLayout.astro
title: Como extraer listado de tags
author: Eva
description: "Listado de tags con la funcion Astro.glob()"
image:
  url: "https://docs.astro.build/_astro/not_found.Bt1vZg-n_1XekVP.webp"
  alt: "Astro glob"
pubDate: 2024-03-31
tags: ["funcion map", "astro.glob"]
---

### explicacion codigo

- const allPosts = await Astro.glob("../posts/\*.md");
- const allTags = [...new Set(allPosts.map((v) => v.frontmatter.tags.flat()))];

El fragmento de código que proporcionaste parece ser parte de un script escrito en JavaScript para un sitio web construido con Astro, un framework de construcción de sitios web estáticos. Aquí te explico lo que hace cada línea:

1. const allPosts = await Astro.glob("../posts/\*.md");

Esta línea utiliza la función glob proporcionada por Astro para encontrar todos los archivos con la extensión .md (Markdown) en el directorio ../posts/ relativo al archivo actual.
await es utilizado para esperar a que la operación asíncrona se complete antes de continuar con la ejecución del script. Esto implica que esta línea de código debe estar dentro de una función async.

2. const allTags = [...new Set(allPosts.map((v) => v.frontmatter.tags.flat()))];

   allPosts.map((v) => v.frontmatter.tags.flat()): Esta parte del código recorre todos los posts obtenidos por Astro.glob y accede a la propiedad frontmatter de cada uno. Se asume que frontmatter es un objeto que contiene metadatos de cada archivo Markdown, y uno de estos metadatos es tags, que sería un array de etiquetas asociadas a cada post.

   .flat(): Como tags puede ser un array de arrays (es decir, un array anidado si un post tiene varias etiquetas), flat() se utiliza para aplanar estos arrays anidados en un único array de etiquetas.

   ...new Set(): Se crea un nuevo objeto Set para eliminar duplicados, ya que Set solo permite valores únicos. Luego, se usa el operador de propagación ... para convertir el Set de nuevo en un array.

   const allTags =: Se declara una constante allTags que almacenará el array de etiquetas únicas.

En resumen, este código está recolectando todas las etiquetas únicas de los archivos Markdown en el directorio de posts y almacenándolas en una constante llamada allTags. Este proceso forma parte de generar una lista de etiquetas para ser usadas en un sitio web, como por ejemplo, para filtrar posts por etiquetas o mostrarlas en una interfaz de usuario.
