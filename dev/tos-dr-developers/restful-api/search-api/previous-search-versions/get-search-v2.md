# GET /search/v2

Search for services in JSON format. This version has been superseded by `GET /search/v3`.

## Endpoint

```
https://api.tosdr.org/search/v2/<query>.json
```

## Parameters

| Parameter | Type   | Description       |
| --------- | ------ | ----------------- |
| query     | String | Your search query |

## Global rate limit

| Benefit | Second | Hour   | Day    |
| ------- | ------ | ------ | ------ |
| Guest   | 15     | 1000   | 15000  |
| Staff   | 15000  | 100000 | 150000 |
| Office  | 15000  | 100000 | 150000 |
| Partner | 150    | 10000  | 50000  |

## Implemented error codes

| Error code   |
| ------------ |
| QUERY_FAILED |

## JSON schema

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
