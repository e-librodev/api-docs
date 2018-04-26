# Errores

La API de e-Libro utiliza el siguiente código de errores:


Código de error | Significado
---------- | -------
400 | Bad Request -- Su request no es válida.
401 | Unauthorized -- Su token es erróneo.
403 | Forbidden -- No tiene permisos para realizar esta request.
404 | Not Found -- No se ha encontrado el elemento solicitado.
405 | Method Not Allowed -- Método no permitido
406 | Not Acceptable -- Ha requerido un formato que no es json.
429 | Too Many Requests -- Ha excedido el límite permitido en cantidad de requests.
500 | Internal Server Error -- Problema interno del servidor. Por favor intente más tarde.
503 | Service Unavailable -- Temporalmente fuera de servicio. Por favor intente más tarde.