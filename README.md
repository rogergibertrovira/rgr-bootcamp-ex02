# rgr-bootcamp-ex02
EX02 - API Clínica Dental, realizada el 20/04/2023

## API endpoints

Listado de los endpoints

|GET|POST|PUT|DELETE|
|---|----|---|------|
|[/api/clientes](#get-apiclientes)|[/api/clientes](#post-apiclientes)|[/api/clientes/{id}](#put-apiclientesid)|[/api/citas/{id}](#delete-apicitasid)|
[/api/dentistas](#get-apidentistas)|[/api/dentistas](#post-apidentistas)|[/api/dentistas/{id}](#put-apidentistasid)|
[/api/citas](#get-apicitas)|[/api/citas](#post-apicitas)|[/api/citas/{id}](#put-apicitasid)|
[/api/clientes/{id}](#get-apiclientesid)|
[/api/dentistas/{id}](#get-apidentistasid)|
[/api/citas/{id}](#get-apicitasid)|
[/api/dentistas/especialidad/{especialidad}](#get-apidentistasespecialidadespecialidad)|
[/api/citas/clienteid/{clienteid}](#get-apicitasclienteidid)|
[/api/citas/dentistaid/{dentistaid}](#get-apicitasdentistaidid)|
___
### GET /api/clientes
Listar todos los clientes

**Respuesta** (ejemplo: /api/clientes)

```
[
    {
        "id": 1,
        "nomApels": "Sinundi Ente",
        "telefono": "652314354",
        "email": "sinundi@email.com"
    },
    {
        "id": 2,
        "nomApels": "Geni Vasrojas",
        "telefono": "633322114",
        "email": "geni@email.com"
    },
    {
        "id": 3,
        "nomApels": "Roger Gibert",
        "telefono": "699847451",
        "email": "roger@email.com"
    }
]
```
___
### GET /api/dentistas
Listar todos los dentistas

**Respuesta** (ejemplo: /api/dentistas)

```
[
    {
        "id": 1,
        "nomApels": "Elsa Cameulas",
        "telefono": "623512557",
        "email": "elsadental@email.com",
        "especialidad": "Odontologia general"
    },
    {
        "id": 2,
        "nomApels": "Dent Ista",
        "telefono": "687549324",
        "email": "dentdental@email.com",
        "especialidad": "Endodoncia"
    },
    {
        "id": 3,
        "nomApels": "Elpone Hierros",
        "telefono": "698563254",
        "email": "elponedental@email.com",
        "especialidad": "Quirofano"
    }
]
```
___
### GET /api/citas
Listar todos las citas

**Respuesta** (ejemplo: /api/citas)

```
[
    {
        "id": 1,
        "fecha": "2023-04-28T12:35:00",
        "tipoIntervencion": "Revision inicial",
        "cliente": {
            "id": 1,
            "nomApels": "Sinundi Ente",
            "telefono": "652314354",
            "email": "sinundi@email.com"
        },
        "dentista": {
            "id": 1,
            "nomApels": "Elsa Cameulas",
            "telefono": "623512557",
            "email": "elsadental@email.com",
            "especialidad": "Odontologia general"
        }
    },
    {
        "id": 2,
        "fecha": "2023-04-30T10:00:00",
        "tipoIntervencion": "Limpieza general",
        "cliente": {
            "id": 3,
            "nomApels": "Roger Gibert",
            "telefono": "699847451",
            "email": "roger@email.com"
        },
        "dentista": {
            "id": 5,
            "nomApels": "Eldien Tesekae",
            "telefono": "687524139",
            "email": "eldiendental@email.com",
            "especialidad": "Limpieza"
        }
    }
]
```
___
### GET /api/clientes/{id}
Buscar un cliente por id

**Respuesta** (ejemplo: /api/clientes/4)

```
{
    "id": 4,
    "nomApels": "Sequedo Sinmuelas",
    "telefono": "656848451",
    "email": "sequedo@email.com"
}
```
___
### GET /api/dentistas/{id}
Buscar un dentista por id

**Respuesta** (ejemplo: /api/dentistas/5)

```
{
    "id": 5,
    "nomApels": "Eldien Tesekae",
    "telefono": "687524139",
    "email": "eldiendental@email.com",
    "especialidad": "Limpieza"
}
```

___
### GET /api/citas/{id}
Buscar una cita por id

**Respuesta** (ejemplo: /api/citas/5)

```
{
    "id": 5,
    "fecha": "2023-04-29T18:50:00",
    "tipoIntervencion": "Ortodoncia superior",
    "cliente": {
        "id": 2,
        "nomApels": "Geni Vasrojas",
        "telefono": "633322114",
        "email": "geni@email.com"
    },
    "dentista": {
        "id": 4,
        "nomApels": "Sakame Lamuela",
        "telefono": "653141247",
        "email": "sakamedental@email.com",
        "especialidad": "Ortodoncias"
   
```

___
### GET /api/dentistas/especialidad/{especialidad}
Buscar un dentista por especialidad

**Respuesta** (ejemplo: /api/dentistas/especialidad/ortodoncias)

```
[
    {
        "id": 2,
        "nomApels": "Dent Ista",
        "telefono": "687549324",
        "email": "dentdental@email.com",
        "especialidad": "Ortodoncias"
    },
    {
        "id": 4,
        "nomApels": "Sakame Lamuela",
        "telefono": "653141247",
        "email": "sakamedental@email.com",
        "especialidad": "Ortodoncias"
    }
]
```

___
### GET /api/citas/clienteid/{id}
Listar todos las citas de un cliente por id

**Respuesta** (ejemplo: /api/citas/clienteid/2)

```
[
    {
        "id": 5,
        "fecha": "2023-04-29T18:50:00",
        "tipoIntervencion": "Ortodoncia superior",
        "cliente": {
            "id": 2,
            "nomApels": "Geni Vasrojas",
            "telefono": "633322114",
            "email": "geni@email.com"
        },
        "dentista": {
            "id": 4,
            "nomApels": "Sakame Lamuela",
            "telefono": "653141247",
            "email": "sakamedental@email.com",
            "especialidad": "Ortodoncias"
        }
    },
    {
        "id": 7,
        "fecha": "2023-04-30T13:15:00",
        "tipoIntervencion": "Revision inicial",
        "cliente": {
            "id": 2,
            "nomApels": "Geni Vasrojas",
            "telefono": "633322114",
            "email": "geni@email.com"
        },
        "dentista": {
            "id": 1,
            "nomApels": "Elsa Cameulas",
            "telefono": "623512557",
            "email": "elsadental@email.com",
            "especialidad": "Odontologia general"
        }
    }
]
```

___
### GET /api/citas/dentistaid/{id}
Listar todos las citas de un dentista por id

**Respuesta** (ejemplo: /api/citas/dentistaid/1)

```
[
    {
        "id": 1,
        "fecha": "2023-04-28T12:35:00",
        "tipoIntervencion": "Revision inicial",
        "cliente": {
            "id": 1,
            "nomApels": "Sinundi Ente",
            "telefono": "652314354",
            "email": "sinundi@email.com"
        },
        "dentista": {
            "id": 1,
            "nomApels": "Elsa Cameulas",
            "telefono": "623512557",
            "email": "elsadental@email.com",
            "especialidad": "Odontologia general"
        }
    },
    {
        "id": 7,
        "fecha": "2023-04-30T13:15:00",
        "tipoIntervencion": "Revision inicial",
        "cliente": {
            "id": 2,
            "nomApels": "Geni Vasrojas",
            "telefono": "633322114",
            "email": "geni@email.com"
        },
        "dentista": {
            "id": 1,
            "nomApels": "Elsa Cameulas",
            "telefono": "623512557",
            "email": "elsadental@email.com",
            "especialidad": "Odontologia general"
        }
    }
]
```

___
### POST /api/clientes
Crear un nuevo cliente

**Parametros** (ejemplo: /api/clientes)
| Nombre   | Tipo | Descripción |   
| -------- | ---- |-------------|
| `nomApels` | STRING | Nombre y apellidos del cliente |
| `telefono` | STRING | Telefono del cliente |
| `email` | STRING | Email del cliente |

___
### POST /api/dentistas
Crear un nuevo dentista

**Parametros** (ejemplo: /api/dentistas)
| Nombre   | Tipo | Descripción |   
| -------- | ---- |-------------|
| `nomApels` | STRING | Nombre y apellidos del dentista |
| `telefono` | STRING | Telefono del dentista |
| `email` | STRING | Email del dentista |
| `especialidad` | STRING | Especialidad del dentista |
___
### POST /api/citas
Crear una nueva cita

**Parametros** (ejemplo: /api/citas)
| Nombre   | Tipo | Descripción |   
| -------- | ---- |-------------|
| `fecha` | DATETIME | Fecha de la cita |
| `tipoIntervencion` | STRING | Tipo de intervención que se realizará |
| `cliente id` | INT | Id del cliente que pide la cita |
| `dentista id` | INT | Id del dentista asignado a la cita |

___
### PUT /api/clientes/{id}
Modificar un cliente existente según el id

**Parametros** (ejemplo: /api/clientes/1)
| Nombre   | Tipo | Descripción |   
| -------- | ---- |-------------|
| `id` | int | Id del cliente |
| `nomApels` | STRING | Nombre y apellidos del cliente |
| `telefono` | STRING | Telefono del cliente |
| `email` | STRING | Email del cliente |

___
### PUT /api/dentistas/{id}
Modificar un dentista existente según el id

**Parametros** (ejemplo: /api/dentistas/1)
| Nombre   | Tipo | Descripción |   
| -------- | ---- |-------------|
| `id` | int | Id del dentista |
| `nomApels` | STRING | Nombre y apellidos del dentista |
| `telefono` | STRING | Telefono del dentista |
| `email` | STRING | Email del dentista |
| `especialidad` | STRING | Especialidad del dentista |

___
### PUT /api/citas/{id}
Modificar una cita existente según el id

**Parametros** (ejemplo: /api/citas/1)
| Nombre   | Tipo | Descripción |   
| -------- | ---- |-------------|
| `id` | INT | Id de la cita |
| `fecha` | DATETIME | Fecha de la cita |
| `tipoIntervencion` | STRING | Tipo de intervención que se realizará |
| `cliente id` | INT | Id del cliente que pide la cita |
| `dentista id` | INT | Id del dentista asignado a la cita |

___
### DELETE /api/citas/{id}
Eliminar una cita existente según el id
(ejemplo: /api/citas/2)
