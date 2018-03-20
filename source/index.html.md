---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell

toc_footers:
  - <a href='https://console.shipit.mx/'>Regístrate para obtener una clave de desarrollador</a>

includes:
  - requests
  - errors
  - orders

search: true
---

# Introducción

La API de ShipIt está organizada en torno a [REST](http://en.wikipedia.org/wiki/Representational_State_Transfer). Nuestra API tiene URL predecibles, orientadas a recursos, y utiliza códigos de respuesta HTTP para indicar errores de la API. Usamos las funciones ya integradas en HTTP, como la autenticación HTTP y los verbos HTTP, que son entendidos por los clientes HTTP estándar. Admitimos el [intercambio de recursos de origen cruzado](http://en.wikipedia.org/wiki/Cross-origin_resource_sharing), lo que le permite interactuar de forma segura con nuestra API desde una aplicación web del lado del cliente (aunque nunca debe exponer su clave API secreta en el código del lado del cliente de ningún sitio web público). [JSON](http://www.json.org/) es devuelto por todas las respuestas de la API, incluidos los errores.

# Authenticación

Autentica tu cuenta incluyendo tu clave secreta en las solicitudes API. Puedes administrar tus claves API en la [consola](https://console.shipit.mx/account/apikeys). Tus claves API tienen muchos privilegios, ¡así que asegúrate de mantenerlas seguras! No compartas tus claves API secretas en áreas de acceso público tales como GitHub, código de cliente, etc.

La autenticación a la API se realiza a través de HTTP Bearer Auth. Proporciona tu clave API como el token de autenticación.

`Authorization: Bearer sk_live_BQokikJOvBiI2HlWgH4olfQ2`

Todas las solicitudes de API se deben realizar a través de HTTPS. Las llamadas realizadas a través de HTTP simple fallarán. Las solicitudes API sin autenticación también fallarán.


> Para autorizar tu petición, usa este código:

```shell
curl "api_endpoint_here"
  -H "Authorization: Bearer sk_live_BQokikJOvBiI2HlWgH4olfQ2"
```

> Asegúrate de reemplazar `sk_live_BQokikJOvBiI2HlWgH4olfQ2` con tu clave de API

<aside class="notice">
Debes de reemplazar <code>sk_live_BQokikJOvBiI2HlWgH4olfQ2</code> con tu clave de API.
</aside>
