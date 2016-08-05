
Para agregar una **nueva sección**, se debe crear un nuevo archivo Markdown en la carpeta en que se encuentran las demás secciones (que ahora solo son Home y Categorías), con la siguiente cabecera:

	layout: page
	title: tituloDeLaSección
	icon: iconoQueRepresentaráLaSección


Para agregar un **nuevo post** (Como son Devops, MBaaS, etc.), se debe crear un nuevo archivo Markdown en la carpeta ***_posts*** con la siguiente cabecera:

	layout: post
	date: fechaDeCreación horaDeCreación
	title: tituloDelPost
	category: categoríaEnQueEstará
	permalink: linkCorto/

Si el post irá en una nueva categoría, solo se debe poner el nombre de ésta en la línea donde se declara la categoría del nuevo post.