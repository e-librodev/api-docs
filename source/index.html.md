---
title: e-Libro API Docs

language_tabs: # must be one of https://git.io/vQNgJ
  - python
  - javascript

toc_footers:
  - <a href='mailto:soporte@e-libro.com'>Solicitar token</a>

includes:
  - errors

search: true
---

# Introducción

¡Bienvenido a la documentación de la API de e-Libro! Puede utilizar nuestra API para acceder mediante los endpoints a la información en nuestras bases de datos.


# Autenticación

Para poder interactuar con nuestra API necesita agregar un token al header de cada request, que tiene la siguiente forma:

`Authorization: Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb`

Este token es provisto por e-Libro. Usted puede solicitar su token a [soporte@e-libro.com](mailto:soporte@e-libro.com)

<!-- > Para autorizar, use el siguiente código:

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

> Asegurese de reemplazar `Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb` con su token. -->

<aside class="notice">
Debe reemplazar <code>Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb</code> con tu token personal.
</aside>

# Títulos

## Obtener títulos

```python
import requests
import json

url = '/api/titles'
headers = {'Authorization': 'Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb'}

try:
    r = requests.get(url, headers=headers)
    data = r.json()
    # Trabajar con el JSON response data
except requests.exceptions.RequestException as e:
    print(e)
    sys.exit(1)
```

```javascript
npm install got

const got = require('got');
var options = {
  json: true,
  headers: {
    'Authorization': 'Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb'
  },
};
(async () => {
  try {
    const response = await got('/api/titles', options);
    // Trabajar el JSON response
  } catch (error) {
    console.log(error.response.body);
  }
})();
```

> El comando de arriba devuelve un JSON estructurado de la siguiente forma:

```json
[
    {
        "isbn": "9788497478083",
        "created": "2018-07-19T23:54:06.045417Z",
        "modified": "2018-07-23T23:59:53.486141Z",
        "publish": false,
        "cdu_code": "",
        "classification_date": null,
        "cover": null,
        "delivery_date": null,
        "description": "",
        "dewey_code": "",
        "drm": false,
        "e_isbn": "",
        "edition": 1,
        "edition_year": "2017",
        "has_audio": false,
        "has_mrc": false,
        "issn": null,
        "lcc_code": "",
        "mupo_price": "4.08",
        "other_id": "",
        "p_isbn": "",
        "pages": 146,
        "publication_date": null,
        "status": "INGRESADO",
        "summary": "",
        "subtitle": "",
        "supo_price": "2.72",
        "title_name": "Apuntes de geometría diferencial de curvas y superficies",
        "toc": [
            {
                "title": "APUNTES DE GEOMETRÍA DIFERENCIAL DE CURVAS (...)",
                "subitems": [
                    {
                        "title": "PÁGINA LEGAL",
                        "page_number": 4
                    },
                    {
                        "title": "ÍNDICE GENERAL",
                        "page_number": 5
                    },
                    {
                        "title": "INTRODUCCIÓN",
                        "page_number": 7
                    },
                    {
                        "title": "1. CURVAS PLANAS",
                        "subitems": [
                            {
                                "title": "1.1. CURVAS PARAMETRIZADAS Y REGULARES",
                                "page_number": 10
                            },
                            {
                                ...,
                            },
                            ...,
                        ],
                        "page_number": 9
                    },
                    {
                        ...,
                    }
                ],
                "page_number": 1
            }
        ],
        "volume": null,
        "verification_date": null,
        "created_by": 12,
        "modified_by": null,
        "audience": null,
        "author": 13,
        "author_right": null,
        "classification": null,
        "classification_user": null,
        "country": null,
        "currency": 5,
        "drm_type": null,
        "language": 8,
        "press": null,
        "primary_bisac": 16,
        "publisher": 38,
        "secundary_bisac": null,
        "subject": 11,
        "verification_user": null,
        "collections": [
            37,
            39,
            43
        ],
        "contributors": [],
        "theme": []
    },
    {
        "isbn": "9788490421987",
        "created": "2018-08-01T19:11:16.342502Z",
        "modified": "2018-08-01T19:11:16.365160Z",
        ...,
    },
    ...
]

```

Este endpoint devuelve todos los títulos (libros, revistas, tesis, manuales, artículos y monografías). Puede reemplazar `titles` por `books`, `magazines`, `thesis`, `manuals`, `articles` o `monographies` para obtener todos los títulos de un tipo específico.

### HTTP Request

HTTP Request | Descripción
--------- | -------
`GET /api/titles` | Devuelve todos los títulos
`GET /api/books` | Devuelve todos los libros
`GET /api/magazines` | Devuelve todas las revistas
`GET /api/thesis` | Devuelve todas las tesis
`GET /api/manuals` | Devuelve todos los manuales
`GET /api/articles` | Devuelve todos los artículos
`GET /api/monographies` | Devuelve todas las monografías


# Autores

## Obtener autores

```python
import requests
import json

url = '/api/authors'
headers = {'Authorization': 'Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb'}

try:
    r = requests.get(url, headers=headers)
    data = r.json()
    # Trabajar con el JSON response data
except requests.exceptions.RequestException as e:
    print(e)
    sys.exit(1)
```

```javascript
npm install got

const got = require('got');
var options = {
  json: true,
  headers: {
    'Authorization': 'Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb'
  },
};
(async () => {
  try {
    const response = await got('/api/authors', options);
    // Trabajar el JSON response
  } catch (error) {
    console.log(error.response.body);
  }
})();
```

> El comando de arriba devuelve un JSON estructurado de la siguiente forma:

```json
[
    {
        "id": 1,
        "created": "2018-06-25T21:56:52.299914Z",
        "modified": null,
        "trash": false,
        "publish": true,
        "order": 0,
        "name": "ABIÁN BENTOR SOCORRO LERÁNOZ",
        "wikipedia": "",
        "twitter": "",
        "created_by": null,
        "modified_by": null
    },
    {
        "id": 3,
        "created": "2018-07-18T19:58:24.309931Z",
        "modified": null,
        "trash": false,
        "publish": true,
        ...,
    },
    ...
]
```

Este endpoint devuelve todos los autores.

### HTTP Request

`GET /api/authors`


## Obtener un autor específico

```python
import requests
import json

url = '/api/authors/1'
headers = {'Authorization': 'Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb'}

try:
    r = requests.get(url, headers=headers)
    data = r.json()
    # Trabajar con el JSON response data
except requests.exceptions.RequestException as e:
    print(e)
    sys.exit(1)
```

```javascript
npm install got

const got = require('got');
var options = {
  json: true,
  headers: {
    'Authorization': 'Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb'
  },
};
(async () => {
  try {
    const response = await got('/api/authors/1', options);
    // Trabajar el response
  } catch (error) {
    console.log(error.response.body);
  }
})();
```

> El comando de arriba devuelve un JSON para el id "1" estructurado de la siguiente forma:

```json
{
    "id": 1,
    "created": "2018-06-25T21:56:52.299914Z",
    "modified": null,
    "trash": false,
    "publish": true,
    "order": 0,
    "name": "ABIÁN BENTOR SOCORRO LERÁNOZ",
    "wikipedia": "",
    "twitter": "",
    "created_by": null,
    "modified_by": null
}
```

Este endpoint devuelve el autor cuyo id es igual a `id`.

### HTTP Request

`GET /api/authors/{id}`

Parámetro | Descripción
--------- | --------------
id | El id del autor

# Editoriales

## Obtener todas las editoriales

```python
import requests
import json

url = '/api/publishers'
headers = {'Authorization': 'Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb'}

try:
    r = requests.get(url, headers=headers)
    data = r.json()
    # Trabajar con el JSON response data
except requests.exceptions.RequestException as e:
    print(e)
    sys.exit(1)
```

```javascript
npm install got

const got = require('got');
var options = {
  json: true,
  headers: {
    'Authorization': 'Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb'
  },
};
(async () => {
  try {
    const response = await got('/api/publishers', options);
    // Trabajar el JSON response
  } catch (error) {
    console.log(error.response.body);
  }
})();
```

> El comando de arriba devuelve un JSON estructurado de la siguiente forma:

```json
[
    {
        "id": 29,
        "created": "2018-07-18T19:45:33.119216Z",
        "modified": "2018-07-18T20:02:50.145842Z",
        "trash": false,
        "publish": true,
        "order": 0,
        "name": "Servicio de Publicaciones. Universidad de Alcalá",
        "url": "http://publicaciones.uah.es/",
        "address": "Pza. San diego, s/n - 28801 Alcalá de Henares (Madrid)",
        "main_phone": "+34918854066",
        "logo": null,
        "created_by": 12,
        "modified_by": 12,
        "country": 213
    },
    {
        "id": 31,
        "created": "2018-07-18T20:14:10.305888Z",
        "modified": null,
        "trash": false,
        "publish": true,
        ...,
    },
    ...
]
```

Este endpoint devuelve todas las editoriales.

### HTTP Request

`GET /api/publishers`


# Contribuidores

## Obtener todos los contribuidores

```python
import requests
import json

url = '/api/contributors'
headers = {'Authorization': 'Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb'}

try:
    r = requests.get(url, headers=headers)
    data = r.json()
    # Trabajar con el JSON response data
except requests.exceptions.RequestException as e:
    print(e)
    sys.exit(1)
```

```javascript
npm install got

const got = require('got');
var options = {
  json: true,
  headers: {
    'Authorization': 'Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb'
  },
};
(async () => {
  try {
    const response = await got('/api/contributors', options);
    // Trabajar el JSON response
  } catch (error) {
    console.log(error.response.body);
  }
})();
```

> El comando de arriba devuelve un JSON estructurado de la siguiente forma:

```json
[
    {
        "id": 1,
        "created": "2018-07-18T20:18:28.798827Z",
        "modified": null,
        "trash": false,
        "publish": true,
        "order": 0,
        "name": "Rubio Núñez Rafael",
        "created_by": 12,
        "modified_by": 12,
        "role": 1,
        "country": null
    },
    {
        "id": 2,
        "created": "2018-07-18T20:43:29.740325Z",
        "modified": null,
        "trash": false,
        "publish": true,
        ...,
    },
    ...
]
```

Este endpoint devuelve todos los contributors.

### HTTP Request

`GET /api/contributors`


## Obtener un contribuidor específico

```python
import requests
import json

url = '/api/contributors/3'
headers = {'Authorization': 'Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb'}

try:
    r = requests.get(url, headers=headers)
    data = r.json()
    # Trabajar con el JSON response data
except requests.exceptions.RequestException as e:
    print(e)
    sys.exit(1)
```

```javascript
npm install got

const got = require('got');
var options = {
  json: true,
  headers: {
    'Authorization': 'Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb'
  },
};
(async () => {
  try {
    const response = await got('/api/contributors/3', options);
    // Trabajar el JSON response
  } catch (error) {
    console.log(error.response.body);
  }
})();
```

> El comando de arriba devuelve un JSON para el contribuidor con id 3, estructurado de la siguiente forma:

```json
{
    "id": 3,
    "created": "2018-07-18T20:43:50.165923Z",
    "modified": null,
    "trash": false,
    "publish": true,
    "order": 0,
    "name": "Oroz Bretón Nekane",
    "created_by": 12,
    "modified_by": 12,
    "role": 1,
    "country": null
}
```

Este endpoint devuelve el contribuidor cuyo id es `id`.

### HTTP Request

`GET /api/contributors/{id}`

Parámetro | Descripción
--------- | --------------
id | El id del contribuidor


## Obtener ciertos contribuidores

```python
import requests
import json

url = '/api/contributors?ids=2,3'
headers = {'Authorization': 'Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb'}

try:
    r = requests.get(url, headers=headers)
    data = r.json()
    # Trabajar con el JSON response data
except requests.exceptions.RequestException as e:
    print(e)
    sys.exit(1)
```

```javascript
npm install got

const got = require('got');
var options = {
  json: true,
  headers: {
    'Authorization': 'Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb'
  },
};
(async () => {
  try {
    const response = await got('/api/contributors?ids=2,3', options);
    // Trabajar el JSON response
  } catch (error) {
    console.log(error.response.body);
  }
})();
```

> El comando de arriba devuelve un JSON para los contribuidores con id 2 y 3, estructurado de la siguiente forma:

```json
[
    {
        "id": 2,
        "created": "2018-07-18T20:43:29.740325Z",
        "modified": null,
        "trash": false,
        "publish": true,
        "order": 0,
        "name": "Socorro Leránoz Abián Bentor",
        "created_by": 12,
        "modified_by": 12,
        "role": 1,
        "country": null
    },
    {
        "id": 3,
        "created": "2018-07-18T20:43:50.165923Z",
        "modified": null,
        "trash": false,
        "publish": true,
        "order": 0,
        "name": "Oroz Bretón Nekane",
        "created_by": 12,
        "modified_by": 12,
        "role": 1,
        "country": null
    }
]
```

Este endpoint devuelve el conjunto de contribuidores cuyos ids son `id1, id2, ..., idN`.

### HTTP Request

`GET /api/contributors?ids=id1, id2, ..., idN`


# Búsquedas

## Búsqueda de títulos

```python
import requests
import json

url = '/api/titles_search/'
headers = {'Authorization': 'Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb'}
body = {
        "channel": "3def3278-9cf8-42a9-838c-b951745faa90",
        "filters": {
            "theme": {
                "value": [1, 2],
                "operation": "in"
            },
            "author__name": {
                "value": "Autor",
                "operation": "icontains"
            },
            "or": { # Se realiza un OR de todos los campos especificados en el objeto
                "publisher__name": {
                    "value": "Editorial1",
                    "operation": "iexact"
                },
                "publisher__name": {
                    "value": "Editorial2",
                    "operation": "iexact"
                },
            }
        },
        "page_size": 3,
        "current_page": 1,
        "include_filters": true # Si es falso la response NO retorna los filtros
    }
try:
    r = requests.post(url, headers=headers, data=body)
    data = r.json()
    # Trabajar con el JSON response data
except requests.exceptions.RequestException as e:
    print(e)
    sys.exit(1)
```

```javascript
npm install got

const got = require('got');
var options = {
    json: true,
    headers: {
        'Authorization': 'Token 55ea9b4aa315cdb10d0d97eb9165fe65c3dafedb'
    },
    body: {
        'channel': '3def3278-9cf8-42a9-838c-b951745faa90',
        'filters': {
            'theme': {
                'value': [1, 2],
                'operation': 'in'
            },
            'author__name': {
                'value': 'Autor',
                'operation': 'icontains'
            },
            'or': { // Se realiza un OR de todos los campos especificados en el objeto
                'publisher__name': {
                    'value': 'Editorial1',
                    'operation': 'iexact'
                },
                'publisher__name': {
                    'value': 'Editorial2',
                    'operation': 'iexact'
                },
            }
        },
        'page_size': 3,
        'current_page': 1,
        'include_filters': true // Si es falso la response NO retorna los filtros
    }
};
(async () => {
    try {
        const response = await got('/api/titles_search/', options);
        // Trabajar el JSON response
    } catch (error) {
        console.log(error.response.body);
    }
})();
```

> El comando de arriba devuelve un JSON estructurado de la siguiente forma:

```json
{
    "results": [
        {
            "title_name": "Destellos de Luz",
            "cover": "url_conver_de_la_imagen",
            "author__name": "Autor 1",
            "isbn": "9788497693066",
            "edition_year": "2000"
        }
    ],
    "filters": [{    --> Si included_filters es true en la request
        "label": "Autores",
        "type": "select",
        "values": [{
           "value": 1,
           "label": "Autor 1"
         }, ...]
    }, ...],
    "total_pages": 1,
    "total_count": 2,
    "current_page": 1
 }
```

Este endpoint devuelve todos los títulos que coinciden con los criterios de búsqueda.

### HTTP Request

`POST /api/titles_search/`