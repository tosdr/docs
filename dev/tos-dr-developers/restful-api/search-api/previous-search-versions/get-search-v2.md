# GET /search/v2

Use this interface to search for a service from our database in json.

\


This API has been superseded by **GET /search/v3/**

**Endpoint**

```
https://api.tosdr.org/search/v2/<query>.json
```

\


#### Parameters <a href="#get-search-v2-parameters" id="get-search-v2-parameters"></a>

| Parameter | Type   | Description       |
| --------- | ------ | ----------------- |
| query     | String | Your search query |

\


#### Global Rate Limit <a href="#get-search-v2-globalratelimit" id="get-search-v2-globalratelimit"></a>

| Benefit | Second | Hour   | Day    |
| ------- | ------ | ------ | ------ |
| Guest   | 15     | 1000   | 15000  |
| Staff   | 15000  | 100000 | 150000 |
| Office  | 15000  | 100000 | 150000 |
| Partner | 150    | 10000  | 50000  |

This rate limit applies to all interfaces. Each Interface and method may implement its own rate limit.

\


#### Implemented Error codes <a href="#get-search-v2-implementederrorcodes" id="get-search-v2-implementederrorcodes"></a>

| Error Code    |
| ------------- |
| QUERY\_FAILED |

\


**JSON Schema**

```
{
    "$schema": "http://json-schema.org/draft-06/schema#",
    "$ref": "#/definitions/Welcome",
    "definitions": {
        "Welcome": {
            "type": "object",
            "additionalProperties": false,
            "properties": {
                "error": {
                    "type": "integer"
                },
                "message": {
                    "type": "string"
                },
                "parameters": {
                    "$ref": "#/definitions/Parameters"
                }
            },
            "required": [],
            "title": "Welcome"
        },
        "Parameters": {
            "type": "object",
            "additionalProperties": false,
            "properties": {
                "service": {
                    "type": "array",
                    "items": {
                        "$ref": "#/definitions/Service"
                    }
                },
                "grid": {
                    "type": "string"
                }
            },
            "required": [],
            "title": "Parameters"
        },
        "Service": {
            "type": "object",
            "additionalProperties": false,
            "properties": {
                "id": {
                    "type": "integer"
                },
                "name": {
                    "type": "string"
                },
                "url": {
                    "type": "string"
                },
                "created_at": {
                    "type": "string"
                },
                "updated_at": {
                    "type": "string"
                },
                "wikipedia": {
                    "anyOf": [
                        {
                            "type": "null"
                        },
                        {
                            "type": "string",
                            "format": "uri",
                            "qt-uri-protocols": [
                                "https"
                            ]
                        }
                    ]
                },
                "keywords": {
                    "type": "string"
                },
                "related": {
                    "type": "string"
                },
                "slug": {
                    "type": "string"
                },
                "is_comprehensively_reviewed": {
                    "type": "boolean"
                },
                "user_id": {
                    "type": "null"
                },
                "rating": {
                    "type": "string"
                },
                "status": {
                    "type": "null"
                },
                "nice_service": {
                    "type": "string"
                },
                "has_image": {
                    "type": "boolean"
                },
                "image": {
                    "type": "string"
                }
            },
            "required": [],
            "title": "Service"
        }
    }
}
```

### Related articles <a href="#get-search-v2-relatedarticles" id="get-search-v2-relatedarticles"></a>

* Page:GET /search/v5
* Page:GET /search/v3
* Page:GET /search/v4

\


\


\
