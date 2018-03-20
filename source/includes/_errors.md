# Errores

ShipIt usa códigos de respuesta HTTP convencionales para indicar el éxito o el fracaso de una solicitud API. En general: los códigos en el rango `2xx` indican éxito. Los códigos en el rango `4xx` indican un error que falló dada la información provista (p. Ej., Se omitió un parámetro requerido, se produjo un error en la carga, etc.). Los códigos en el rango `5xx` indican un error con los servidores de ShipIt (estos son raros).

Sin embargo, no todos los errores se mapean limpiamente en los códigos de respuesta HTTP. Cuando una solicitud es válida pero no se completa con éxito (por ejemplo, el código de rastreo es incorrecto), devolvemos un código de error `402`. Para entender por qué se rechaza una tarjeta, consulte la lista de códigos de rechazo de ShipIt.


Error Code | Meaning
---------- | -------
400 | Bad Request -- Your request is invalid.
401 | Unauthorized -- Your API key is wrong.
403 | Forbidden -- The kitten requested is hidden for administrators only.
404 | Not Found -- The specified kitten could not be found.
405 | Method Not Allowed -- You tried to access a kitten with an invalid method.
406 | Not Acceptable -- You requested a format that isn't json.
410 | Gone -- The kitten requested has been removed from our servers.
418 | I'm a teapot.
429 | Too Many Requests -- You're requesting too many kittens! Slow down!
500 | Internal Server Error -- We had a problem with our server. Try again later.
503 | Service Unavailable -- We're temporarily offline for maintenance. Please try again later.
