# Mis notas sobre Ciberseguridad

![GitHub commit activity](https://img.shields.io/github/commit-activity/m/Hacknarok/infosec?color=22A7F0)

Este repositorio contiene una **bóveda de [Obsidian][obsidian]** que contiene notas sobre distintos aspectos de la **informática** en general, pero orientados a la **ciberseguridad** (de ahí el nombre tan original, *InfoSec*).

![Grafo.png](https://github.com/Hacknarok/infosec/blob/master/recursos/README/Grafo.png)

 La bóveda está formada por notas sobre todo lo que voy -y vaya- aprendiendo a lo largo del tiempo: textos, citas, apuntes, imágenes, enlaces, redacciones de "prácticas"...

 Además de algunas notas más "personales" (objetivos, "registros"...), porque esto no deja de ser *algo que hago yo para mí, pero que no me importa que sea público por si ayuda*.



## Objetivos del repositorio

Usaré Github para sustituir los servicios de suscripción que ofrece [Obsidian][obsidian].

### Sincronización

Usando un repositorio, puedo clonarlo en todos los ordenadores que quiera y acceder al contenido.
- Sustituyo [Sync][sync], pero debo sincronizar mis notas manualmente.

### Seguridad

Usando un repositorio, puedo llevar un seguimiento de las versiones de mis notas y recuperar esa información en cualquier momento.
- Sustituyo [Sync][sync], pero creo que mejor, porque en mi caso puedo consultar versiones.

### Publicación (indirectamente)

Pese a que este es un **proyecto personal**, he pensado que podría resultar útil que fuera público para que todo aquel que esté interesado en este tema pueda acceder a él. Yo estoy abierto a compartir e incluso ampliar mi conocimiento con otras personas, pero me gustaría aclarar que eso **es una consecuencia** de haber decidido hacer público este repositorio, **no la causa** por la que lo he hecho público.
- Sustituyo [Publish][publish].

> Este README está escrito con la intención de guiar a alguien que considere usar este material.


## ¿Qué es Obsidian?

He mencionado (y enlazado) mucho este programa, pero si estás leyendo esto y no sabes qué es, quizás no te estés enterando.

[Obsidian][obsidian] es una aplicación para **tomar notas**, que se caracteriza principalmente por ser: simple, ligera y flexible (extensible mediante [plugins](https://obsidian.md/plugins)).

![Workspace.png](https://github.com/Hacknarok/infosec/blob/master/recursos/README/Workspace.png)

Este programa lo único que hace es renderizar ficheros en formato [Markdown][MD] y añadir otras funciones (notas enlazadas, etiquetas, alias de notas, grafos de conexiones...), de ahí su simpleza y a la vez, su extensibilidad.

> Si quieres una guía rápida y sencilla para saber cómo escribir en formato [Markdown][MD], te dejo una que hice [aquí][guia].

### Qué es una bóveda

Una **bóveda** es simplemente, una **carpeta con archivos que [Obsidian][obsidian] lee e interpreta** para activar sus funcionalidades. Su estructura/contenido puede diferenciarse en 2 partes:
- Una carpeta de configuración (`.obsidian`): indica a [Obsidian][obsidian] qué plugins, temas, workspaces y el estado más reciente de la bóveda.
- Las notas (archivos `.md`) y su multimedia (imágenes, vídeos, audios...): el "contenido" de la bóveda.

```
Bóveda
├-- .obsidian
|   ├-- plugins
|   ├-- themes
|   ├-- graph.js
|   ├-- workspace
|   └-- (...)
├-- Nota1.md
├-- Nota2.md
├-- Subcarpeta
|   ├-- Imagen3.png
|   └-- Nota3.md
└-- (...)
```


## Cómo usar el contenido del repositorio

Teniendo en cuenta lo mencionado sobre [Obsidian][obsidian], siempre vas a poder leer las notas *a pelo* (en texto plano) porque el contenido está escrito en [Markdown][MD]; sin embargo, la experiencia mejora enormemente usando la aplicación.

### Notas de la bóveda

1. Descargar [Obsidian][obsidian].
2. Clonar este repositorio.
3. Arrancar [Obsidian][obsidian] y seleccionar "Abrir carpeta como bóveda".
4. Seleccionar la carpeta *[InfoSec](https://github.com/Hacknarok/infosec/tree/master/InfoSec)* del repositorio.

Esto permite el acceso al "material" de la bóveda y su sincronización.


### Configuración de la bóveda

1. Copiar la carpeta `recursos/.obsidian` dentro de la bóveda (*[InfoSec](https://github.com/Hacknarok/infosec/tree/master/InfoSec)*).

Esto permite activar los plugins, los colores y el workspace estándar que he dejado preparados.

Esta carpeta está por separado porque sus archivos se actualizan prácticamente cada vez que se usa la aplicación, por lo que resulta incómodo tener que hacerles seguimiento; separándola y luego añadiéndola manualmente permite que la configuración sea independiente.


## Nota

La configuración que comparto tiene el plugin ***[Obsidian Git][obsidian-git]***, por lo que podrás actualizar el contenido del repositorio (e incluso automatizarlo) desde la propia aplicación de [Obsidian][obsidian], sin tener que ejecutar los comandos de `git` desde una consola externa.

**ADVERTENCIA:** Este plugin requiere que tengas las credenciales de git guardadas para funcionar adecuadamente, y en Linux solo es compatible (por ahora) con la `AppImage` de [Obsidian][obsidian].

> Si quieres una guía sobre cómo usar Git, te dejo una que hice [aquí](https://www.notion.so/srgalan-aprendizaje/Mi-curso-de-Git-a44556d305554f31a2eb50044add5b95#2931120420154b2ab850c02a0e9e3f69) (viene descrito **cómo almacenar las credenciales de git**).

[obsidian]: https://obsidian.md
    [sync]: https://obsidian.md/sync
    [publish]: https://obsidian.md/publish
[MD]: https://es.wikipedia.org/wiki/Markdown
    [guia]: https://srgalan-aprendizaje.notion.site/Markdown-18a13c7236b2434fb60a45b67482741d
    [obsidian-git]: https://github.com/denolehov/obsidian-git
