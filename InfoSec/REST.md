---
aliases: [R.E.S.T, RESTful]
tags:    [concepto, arquitectura]
---

# Introducción
Arquitectura de [[Servicio Web]] donde cada [[URL]] única representa un objeto individual de algún tipo.
> [!INFO] Siglas
> **Re**presentational **S**tate **T**ransfer
> *Transferencia de Estado Representativo*

> [!TODO] Curiosidad
> La arquitectura [[Servicio Web#R E S T|REST]] original fue diseñada por uno de los principales autores de [[HTTP]], [[Roy Fielding]].


# Características
- **Usa [[HTTP]]** y reutiliza varios de sus [[HTTP#Métodos|métodos]].
	-> También ofrece servicios sencillos orientados a [[CRUD]].
- **No tiene estados**, ni el [[Cliente|cliente]] ni el [[Servidor|servidor]] almacenan información de las transacciones.
	-> No obstante, el [[Servidor|servidor]] puede implementar [[Caché|caché]] para las de tipo `GET`. 
- El [[Cliente|cliente]] y el [[Servidor|servidor]] son **independientes entre sí**.
	-> Diferentes lenguajes de programación, frameworks...

## Peticiones
Las peticiones están compuestas de 3 elementos:

### Peticiones [[HTTP]]
Ejemplos: `GET`, `POST`, `PUT`, `PATCH`, `DELETE`...

| Verbo           | Función del cliente                        |
|:---------------:|:-------------------------------------------|
| `GET`           | Solicitar un recurso al servidor           |
| `POST`          | Crear un recurso en el servidor            |
| `PUT`/`PATCH`   | Editar recursos existentes en el servidor  |
| `DELETE`        | Eliminar un recurso en el servidor         |
^5e14f6

#### Comparativas con otros lenguajes
| Lenguaje | Crear    | Leer     | Actualizar | Borrar   |
|:--------:|:--------:|:--------:|:----------:|:--------:|
| HTTP     | `POST`   | `GET`    | `PUT`      | `DELETE` |
| SQL      | `INSERT` | `SELECT` | `UPDATE`   | `DELETE` |

### Dirección [[URI]]
Ejemplo: `http://mipagina.com/api/v1/foto`

### Datos formateados
Ejemplos: formatos como [[XML]], [[JSON]], o en [[Binario]].

## Respuestas
Cada petición genera un código de respuesta, que indica el estado de dicha petición.
| Formato | Significado        |
|:-------:|:------------------:|
| `1xx`   | Información        |
| `2xx`   | Correcto           |
| `3xx`   | Redirección        |
| `4xx`   | Error del cliente  |
| `5xx`   | Error del servidor |

