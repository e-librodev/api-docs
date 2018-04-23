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
curl "/api/titulos"
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
`GET /api/titulos` | Devuelve todos los títulos
`GET /api/libros` | Devuelve todos los libros
`GET /api/revistas` | Devuelve todas las revistas
`GET /api/tesis` | Devuelve todas las tesis
`GET /api/manuales` | Devuelve todos los manuales
`GET /api/articulos` | Devuelve todos los artículos
`GET /api/monografias` | Devuelve todas las monografías


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
curl "/api/autores"
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

`GET /api/autores`


## Obtener un autor

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
curl "/api/autores/1"
  -H "Authorization: Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb');
let kittens = api.kittens.get();
```

> El comando de arriba devuelve un JSON para el id "1" estructurado de la siguiente forma:

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
  }
]
```

Este endpoint devuelve el autor con el id `id`.

### HTTP Request

`GET /api/autores/id` donde `id` es el id del autor

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
curl "/api/editoriales"
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

`GET /api/editoriales`


# Contribuidores

## Obtener todos los contribuidores

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
curl "/api/contribuidores"
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

`GET /api/contribuidores`


## Obtener un contribuidor específico

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
curl "/api/contribuidores/3"
  -H "Authorization: Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb');
let kittens = api.kittens.get();
```

> El comando de arriba devuelve un JSON para el contribuidor con id 3, estructurado de la siguiente forma:

```json
[
  {
    "id": 3,
    "creado": "2018-02-06T22:50:11.809266Z",
    "modificado": null,
    "basura": false,
    "publicado": true,
    "orden": 3,
    "nombre": "Rafael Rubio Núñez",
    "creado_por": 1,
    "modificado_por": 1,
    "rol": 1,
    "pais": null
  }
]
```

Este endpoint devuelve el contribuidor con id `id`.

### HTTP Request

`GET /api/contribuidores/id`



## Obtener ciertos contribuidores

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
curl "/api/contribuidores?ids=(2,3)"
  -H "Authorization: Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb');
let kittens = api.kittens.get();
```

> El comando de arriba devuelve un JSON para los contribuidores con id 2 y 3, estructurado de la siguiente forma:

```json
[
  {
    "id": 2,
    "creado": "2018-02-06T22:02:45.864183Z",
    "modificado": null,
    "basura": false,
    "publicado": true,
    "orden": 2,
    "nombre": "Nekane Oroz Bretón",
    "creado_por": 1,
    "modificado_por": 1,
    "rol": 1,
    "pais": null
  },
  {
    "id": 3,
    "creado": "2018-02-06T22:50:11.809266Z",
    "modificado": null,
    "basura": false,
    "publicado": true,
    "orden": 3,
    "nombre": "Rafael Rubio Núñez",
    "creado_por": 1,
    "modificado_por": 1,
    "rol": 1,
    "pais": null
  }
]
```

Este endpoint devuelve el conjunto de contribuidores con ids `(id1, id2, ..., idN)`.

### HTTP Request

`GET /api/contribuidores?ids=(id1, id2, ..., idN)`

# Usuarios

## Usuarios E-Reader

### Crear usuario EReaderUser

Usuarios `APIUser` pueden utilizar la API para crear usuarios de tipo `EReaderUser` el cual tiene acceso al lector. Para crear un usuario de este tipo, se hace un a request a `/api/ereaderusers/`

`POST /api/ereaderusers/`

```
POST /api/ereaderusers/
{
    "email": "correo@dominio.com",
    "password": "password",
    "company": "mycompany"
}
```

El valor de company debe ser el nombre de la compañia asociada al APIUser que esta haciendo la request.

