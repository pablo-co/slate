# Ordenes


## El objeto Orden

Las ordenes representan un grupo de artículos que deben de ser enviados a un cliente. Dentro de la plataforma es posible elegir el número y tamaño de las cajas en las que se van a enviar los artículos.

```json
{
  "id": "2xm8L7dvkLsqz0DJILbP",
  "type": "Order",
  "status": "Pending",
  "internalCode": "7812",
  "customer": {
    "name": "Ramon Camo",
    "email": "ramon@gmail.com",
    "phone": "+525528674362"
  },
  "items": [
    {
       "name": "Lentes Rayban",
       "sku": "rayban-lg-12",
       "quantity": 2
    }
  ],
  "shippingAddress": {
    "street1": "Avenida de los Bosques 32",
    "street2": "Depto 232",
    "city": "Naucalpan",
    "state": "Edo de Mex",
    "postalCode": 53960,
    "country": "MX"
  },
  "createdAt": "2018-03-18T03:31:32.367Z"
}
```

Atributo | Descripción
--------- | -----------
id | Identificador único para el objeto
type | Cadena que representa el tipo del objeto. Los objetos del mismo tipo comparten el mismo valor.
status | Estado en el que se encuentra la orden.
internalCode | El código interno usado en el negocio. Este identificador te ayudará a identificar esta orden en el sistema.
customer | Información sobre el cliente 
items | Lista de productos o cosas asociadas a la orden.
shippingAddress | Dirección a la que se van a mandar los productos.
createdAt | Hora en la que se creó el objeto. En formato [ISO 8601](https://en.wikipedia.org/wiki/ISO_8601).

### Cliente (Customer)

El nombre, teléfono y en algunos casos el email es información necesaria para la
generación de las guías.

```json
{
  "name": "Ramon Camu",
  "email": "ramon@gmail.com",
  "phone": "+525528674362"
}
```

Atributo | Descripción
--------- | -----------
name | El nombre del cliente
email | El email del cliente
phone | El teléfono del cliente


### Artículo (Item)

```json
{
  "name": "Lentes Rayban",
  "sku": "rayban-lg-12",
  "quantity": 2
}
```

Atributo | Descripción
--------- | -----------
name | Nombre del artículo.
sku | El [SKU](https://en.wikipedia.org/wiki/Stock_keeping_unit) del artículo.
quantity | Número de artículos de este tipo.

```json
{
  "street1": "Avenida de los Bosques 32",
  "street2": "Depto 232",
  "city": "Naucalpan",
  "state": "Edo de Mex",
  "postalCode": 53960,
  "country": "MX"
}
```

### Dirección (Address)

Atributo | Descripción
--------- | -----------
street1 | Primera línea de la dirección
street2 | Segunda línea de la dirección
city | Delegación/Municipio  donde se encuentra la dirección
state | Estado o provincia donde se encuentra la dirección
postalCode | Código postal en el que se encuentra la dirección
country | Código de país [ISO 3166](http://www.iso.org/iso/country_codes) para el país en el que se encuentra la dirección


## Crear una orden

```shell
curl https://api.shipit.mx/v1/orders \
  -H "Authorization: Bearer sk_live_BQokikJOvBiI2HlWgH4olfQ2" \
  -d internalCode="7812" \
  -d customer[name]="Ramon Camo" \
  -d customer[email]="ramon@gmail.com" \
  -d customer[phone]="+525528674362" \
  -d items[0][name]="Lentes Rayban" \
  -d items[0][sku]="rayban-lg-12" \
  -d items[0][quantity]=2 \
  -d shippingAddress[street1]="Avenida de los Bosques 32" \
  -d shippingAddress[street2]="Depto 232" \
  -d shippingAddress[city]="Naucalpan" \
  -d shippingAddress[state]="Edo. de Mex" \
  -d shippingAddress[postalCode]="53960" \
  -d shippingAddress[country]="MX"
```

> El comando anterior devuelve JSON estructurado de la siguiente manera:

```json
{
  "id": "2xm8L7dvkLsqz0DJILbP",
  "type": "Order",
  "status": "Pending",
  "internalCode": "7812",
  "customer": {
    "name": "Ramon Camo",
    "email": "ramon@gmail.com",
    "phone": "+525528674362"
  },
  "items": [
    {
       "name": "Lentes Rayban",
       "sku": "rayban-lg-12",
       "quantity": 2
    }
  ],
  "shippingAddress": {
    "street1": "Avenida de los Bosques 32",
    "street2": "Depto 232",
    "city": "Naucalpan",
    "state": "Edo de Mex",
    "postalCode": 53960,
    "country": "MX"
  },
  "createdAt": "2018-03-18T03:31:32.367Z"
}
```

Las ordenes representan un grupo de artículos que deben de ser enviados a un cliente. Dentro de la plataforma es posible elegir el número y tamaño de las cajas en las que se van a enviar los artículos.


### Solicitud HTTP

`POST https://api.shipit.mx/v1/orders`

### Pametros

Parametro | Requerido
--------- | -------
internalCode | Sí
[customer](#cliente-customer) | Sí
[items](#articulo-item) | Sí
[shippingAddress](#direccion-shippingaddress) | Sí
