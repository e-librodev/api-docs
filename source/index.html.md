---
title: e-Libro API Docs

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - ruby
  - python
  - javascript

toc_footers:
  - <a href='#'>Solicitar token</a>

includes:
  - errors

search: true
---

# Introducción

¡Bienvenido a la documentación de la API de e-Libro! Puede utilizar nuestra API para acceder mediante los endpoints a la información en nuestras bases de datos.


# Autenticación

Para poder interactuar con nuestra API necesita agregar un token al header de cada request, que tiene la siguiente forma:

`Authorization: Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb`

Este token es provisto por e-Libro. Usted puede [solicitar su token](#)

> Para autorizar, use el siguiente código:

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb')
```

```python
import kittn

api = kittn.authorize('Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb')
```

```shell
# Con la consola, usted puede pasar el header correcto con cada request
curl "api_endpoint_here"
  -H "Authorization: Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb');
```

> Asegurese de reemplazar `Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb` con su token.

<aside class="notice">
Debe reemplazar <code>Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb</code> con tu token personal.
</aside>

# Títulos

## Obtener títulos

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb')
api.kittens.get()
```

```shell
curl "http://elibro.net/api/titulos"
  -H "Authorization: Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb');
let kittens = api.kittens.get();
```

> El comando de arriba devuelve un JSON estructurado de la siguiente forma:

```json
[
  {
    "id": 6,
    "creado": "2018-03-05T19:51:42.839641Z",
    "modificado": null,
    "publicado": true,
    "id_elibro": "2b9e9c59-9b73-496a-b7fa-3f33185f4206",
    "drm": false,
    "titulo": "Crimen y castigo. Tomo II",
    "subtitulo": "",
    "precio": "52.10",
    "precio_mupo": "0.00",
    "precio_supo": "0.00",
    "isbn": "9781449234782",
    "e_isbn": "",
    "otro_id": "",
    "volumen": null,
    "edicion": null,
    "fecha_entrega": "2014-04-06",
    "fecha_publicacion": "2018-03-05",
    "numero_copias": null,
    "numero_paginas": 521,
    "portada": null,
    "resumen": "",
    "descripcion": "",
    "ano_edicion": "2014",
    "toc": null,
    "creado_por": 3,
    "modificado_por": 3,
    "audiencia": null,
    "materia": 6,
    "tipo_drm": null,
    "idioma": 8,
    "bisac_primario": 6,
    "bisac_secundario": null,
    "clasificacion": null,
    "derecho": null,
    "autor": 4,
    "imprenta": null,
    "moneda": 5,
    "pais": 11,
    "editorial": 18,
    "colecciones": [
      14
    ],
    "contribuidores": [
      4
    ]
  },
  {
    "id": 6,
    "creado": "2018-03-05T19:51:42.839641Z",
    "modificado": null,
    "publicado": true,
    ...,
    ...,
  }
]
```

Este endpoint devuelve todos los títulos (libros, revistas, tesis, manuales, artículos y monografías). Puede reemplazar `titulos` por `libros`, `revistas`, `tesis`, `manuales`, `articulos` o `monografias` para obtener todos los títulos de un tipo específico.

### HTTP Request

HTTP Request | Descripción
--------- | -------
`GET http://elibro.net/api/titulos` | Devuelve todos los títulos
`GET http://elibro.net/api/libros` | Devuelve todos los libros
`GET http://elibro.net/api/revistas` | Devuelve todas las revistas
`GET http://elibro.net/api/tesis` | Devuelve todas las tesis
`GET http://elibro.net/api/manuales` | Devuelve todos los manuales
`GET http://elibro.net/api/articulos` | Devuelve todos los artículos
`GET http://elibro.net/api/monografias` | Devuelve todas las monografías


## Obtener headers de títulos

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb')
api.kittens.get()
```

```shell
curl "http://elibro.net/api/title_headers?model=Libro"
  -H "Authorization: Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb');
let kittens = api.kittens.get();
```

> El comando de arriba devuelve para el ejemplo de la tabla "Libro" un JSON estructurado de la siguiente forma:

```json
[
    "titulo",
    "subtitulo",
    "precio",
    "precio_mupo",
    "precio_supo",
    "isbn",
    "e_isbn",
    "otro_id",
    "volumen",
    "edicion",
    "fecha_entrega",
    "fecha_publicacion",
    "numero_copias",
    "resumen",
    "descripcion",
    "ano_edicion",
    "audiencia",
    "materia",
    "idioma",
    "bisac_primario",
    "bisac_secundario",
    "clasificacion",
    "derecho",
    "autor",
    "imprenta",
    "moneda",
    "pais",
    "editorial",
    "colecciones",
    "contribuidores"
]
```

Este endpoint devuelve los nombres de las columnas de la tabla del título especificado (Libro, Revista, Tesis, Manual, Articulo, Monografia).

### HTTP Request

`GET http://elibro.net/api/title_headers?model=Parametro`

### Parametros de la query

Parametro de la query | Descripción
--------- | -------
Libro | Devuelve los nombres de las columnas de la tabla Libro
Revista | Devuelve los nombres de las columnas de la tabla Revista
Tesis | Devuelve los nombres de las columnas de la tabla Tesis
Manual | Devuelve los nombres de las columnas de la tabla Manual
Articulo | Devuelve los nombres de las columnas de la tabla Articulo
Monografia | Devuelve los nombres de las columnas de la tabla Monografia


# Autores

## Obtener autores

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb')
api.kittens.get()
```

```shell
curl "http://elibro.net/api/autores"
  -H "Authorization: Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb');
let kittens = api.kittens.get();
```

> El comando de arriba devuelve un JSON estructurado de la siguiente forma:

```json
[
  {
    "id": 1,
    "creado": "2018-02-06T21:58:32.636596Z",
    "modificado": null,
    "basura": false,
    "publicado": true,
    "orden": 1,
    "nombre": "Carlos Sáenz Gamasa",
    "wikipedia": "",
    "twitter": "",
    "creado_por": 1,
    "modificado_por": 1
  },
  {
    "id": 2,
    "creado": "2018-02-06T22:35:49.163085Z",
    "modificado": null,
    "basura": false,
    "publicado": true,
    ...,
    ...,
  }
]
```

Este endpoint devuelve todos los autores.

### HTTP Request

`GET http://elibro.net/api/autores`


# Editoriales

## Obtener editoriales

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb')
api.kittens.get()
```

```shell
curl "http://elibro.net/api/editoriales"
  -H "Authorization: Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb');
let kittens = api.kittens.get();
```

> El comando de arriba devuelve un JSON estructurado de la siguiente forma:

```json
[
  {
    "id": 4,
    "creado": "2018-02-23T21:40:12.805870Z",
    "modificado": "2018-03-02T02:48:13.419902Z",
    "basura": false,
    "publicado": true,
    "orden": 1,
    "nombre": "Editorial UOC",
    "url": "http://www.editorialuoc.cat/",
    "direccion": "Rambla del Poblenou, núm. 156\r\n08018 Barcelona",
    "telefono_principal": "93 486 39 40",
    "logo": null,
    "creado_por": 1,
    "modificado_por": 1,
    "pais": 213
  },
  {
    "id": 5,
    "creado": "2018-03-02T02:43:53.904328Z",
    "modificado": "2018-03-02T02:48:21.386334Z",
    "basura": false,
    "publicado": true,
    ...,
    ...,
  }
]
```

Este endpoint devuelve todas las editoriales.

### HTTP Request

`GET http://elibro.net/api/editoriales`


# Contribuidores

## Obtener contribuidores

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb')
api.kittens.get()
```

```shell
curl "http://elibro.net/api/contribuidores"
  -H "Authorization: Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb');
let kittens = api.kittens.get();
```

> El comando de arriba devuelve un JSON estructurado de la siguiente forma:

```json
[
  {
    "id": 1,
    "creado": "2018-02-06T22:02:04.565059Z",
    "modificado": null,
    "basura": false,
    "publicado": true,
    "orden": 1,
    "nombre": "Abián Bentor Socorro Leránoz",
    "creado_por": 1,
    "modificado_por": 1,
    "rol": 1,
    "pais": null
  },
  {
    "id": 2,
    "creado": "2018-02-06T22:02:45.864183Z",
    "modificado": null,
    "basura": false,
    "publicado": true,
    "orden": 2,
    "nombre": "Nekane Oroz Bretón",
    ...,
    ...,
  }
]
```

Este endpoint devuelve todos los contribuidores.

### HTTP Request

`GET http://elibro.net/api/contribuidores`


# Lector

## Colores

### Obtener colores

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb')
api.kittens.get()
```

```shell
curl "http://elibro.net/api/colores"
  -H "Authorization: Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb');
let kittens = api.kittens.get();
```

> El comando de arriba devuelve un JSON estructurado de la siguiente forma:

```json
[
  {
    "id": 1,
    "creado": "2018-04-10T16:59:16.647842Z",
    "modificado": "2018-04-10T17:00:36.643260Z",
    "basura": false,
    "publicado": true,
    "orden": 0,
    "nombre": "Rojo",
    "hex_color": "red",
    "creado_por": 1,
    "modificado_por": 1
  },
  {
    "id": 2,
    "creado": "2018-04-10T17:00:50.367846Z",
    "modificado": null,
    "basura": false,
    "publicado": true,
    "orden": 0,
    "nombre": "Violeta",
    ...,
    ...,
  }
]
```

Este endpoint devuelve todos los colores.

#### HTTP Request

`GET http://elibro.net/api/colores`


## Sombreados

### Obtener sombreados

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb')
api.kittens.get()
```

```shell
curl "http://elibro.net/api/sombreados"
  -H "Authorization: Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb');
let kittens = api.kittens.get();
```

> El comando de arriba devuelve un JSON estructurado de la siguiente forma:

```json
[
  {
    "id": 16,
    "creado": "2018-04-15T00:11:57.482429Z",
    "modificado": null,
    "basura": false,
    "publicado": false,
    "orden": 0,
    "numero_pagina": 229,
    "area": [
      {
        "bbox": {
          "x0": 352,
          "x1": 446,
          "y0": 547,
          "y1": 576
        },
        "text": "popular",
        "baseline": {
          "x0": 352,
          "x1": 446,
          "y0": 569,
          "y1": 569,
          "has_baseline": true
        }
      },
      {
        "bbox": {
            ...
        },
        "text": ...,
        "baseline": {
            ...
        }
      },
      ...,
    ],
    "texto": "popular se encuentra profundamente arraigado el temor a la oscu- ridad, a la falta de luz.",
    "creado_por": 1,
    "modificado_por": 1,
    "usuario": 1,
    "titulo": 4,
    "color": 1
  },
  {
    "id": 10,
    "creado": "2018-04-10T17:08:04.345498Z",
    "modificado": null,
    "basura": false,
    "publicado": false,
    ...,
    ...,
  }
]
```

Este endpoint devuelve todos los sombreados.

#### HTTP Request

`GET http://elibro.net/api/sombreados`


## Marcadores

### Obtener marcadores

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb')
api.kittens.get()
```

```shell
curl "http://elibro.net/api/marcadores"
  -H "Authorization: Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb');
let kittens = api.kittens.get();
```

> El comando de arriba devuelve un JSON estructurado de la siguiente forma:

```json
[
  {
    "id": 1,
    "creado": "2018-04-08T00:46:55.437564Z",
    "modificado": null,
    "basura": false,
    "publicado": false,
    "orden": 0,
    "numero_pagina": 24,
    "creado_por": 1,
    "modificado_por": 1,
    "usuario": 1,
    "titulo": 4
  },
  {
    "id": 2,
    "creado": "2018-04-10T23:38:34.292736Z",
    "modificado": null,
    "basura": false,
    "publicado": false,
    "orden": 0,
    "numero_pagina": 71,
    "creado_por": 1,
    "modificado_por": 1,
    "usuario": 1,
    "titulo": 4
  }
]
```

Este endpoint devuelve todos los marcadores.

#### HTTP Request

`GET http://elibro.net/api/marcadores`


## Anotaciones

### Obtener anotaciones

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb')
api.kittens.get()
```

```shell
curl "http://elibro.net/api/anotaciones"
  -H "Authorization: Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb');
let kittens = api.kittens.get();
```

> El comando de arriba devuelve un JSON estructurado de la siguiente forma:

```json
[
  {
    "id": 1,
    "creado": "2018-04-10T23:38:04.346830Z",
    "modificado": null,
    "basura": false,
    "publicado": false,
    "orden": 0,
    "texto": "Hola Rafa!",
    "numero_pagina": 133,
    "creado_por": 1,
    "modificado_por": 1,
    "usuario": 1,
    "titulo": 4
  },
  {
    "id": 2,
    "creado": "2018-04-18T21:11:50.116815Z",
    "modificado": null,
    "basura": false,
    "publicado": false,
    "orden": 0,
    "texto": "Hola Carlos",
    "numero_pagina": 97,
    "creado_por": 1,
    "modificado_por": 1,
    "usuario": 1,
    "titulo": 4
  }
]
```

Este endpoint devuelve todas las anotaciones.

#### HTTP Request

`GET http://elibro.net/api/anotaciones`


# Usuarios

## Usuarios de la plataforma

### Obtener usuarios

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb')
api.kittens.get()
```

```shell
curl "http://elibro.net/api/users"
  -H "Authorization: Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb');
let kittens = api.kittens.get();
```

> El comando de arriba devuelve un JSON estructurado de la siguiente forma:

```json
[
  {
    "id": 7,
    "email": "cienciahoy2015@gmail.com",
    "first_name": "Ana",
    "last_name": "",
    "foto": null
  },
  {
    "id": 1,
    "email": "admin@admin.com",
    "first_name": "Admin",
    "last_name": "Istrador",
    "foto": "https://elibro-media.s3.amazonaws.com/library_center/profile/2018/02/20180226223200.jpg"
  },
]
```

Este endpoint devuelve todos las usuarios de la plataforma.

#### HTTP Request

`GET http://elibro.net/api/users`


## Usuarios E-Reader

### Obtener EReaderUsers

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb')
api.kittens.get()
```

```shell
curl "http://elibro.net/api/ereaderusers"
  -H "Authorization: Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb');
let kittens = api.kittens.get();
```

> El comando de arriba devuelve un JSON estructurado de la siguiente forma:

```json

ERROR 500. VER

```

Este endpoint devuelve todos los usuarios con acceso al lector.

#### HTTP Request

`GET http://elibro.net/api/ereaderusers`

### Crear usuario EReaderUser

Usuarios `APIUser` pueden utilizar la API para crear usuarios de tipo `EReaderUser` el cual tiene acceso al lector. Para crear un usuario de este tipo, se hace un a request a `/api/ereaderusers/`

```
POST /api/ereaderusers/

{
    "email": "correo@dominio.com",
    "password": "password",
    "company": "mycompany"
}
```

El valor de company debe ser el nombre de la compañia asociada al APIUser que esta haciendo la request.

