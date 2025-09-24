# GET /document/v1

Use this interface to retrieve a document from our database.

## Endpoint

```
https://api.tosdr.org/document/v1
```

## Parameters

| Parameter | Type    | Description                                                              |
| --------- | ------- | ------------------------------------------------------------------------ |
| id        | Integer | Document ID to retrieve. Omit the parameter to list all document IDs and `text_version` values. |

## Repository

[https://github.com/tosdr/API/tree/master/functions/public/Document/GET/v1](https://github.com/tosdr/API/tree/master/functions/public/Document/GET/v1)

## Implemented error codes

| Error                             | HTTP status | Bitmask            |
| --------------------------------- | ----------- | ------------------ |
| An invalid doc id has been supplied | 404         | `INVALID_PARAMETER` |

## Example response

```
{
  "error": 256,
  "message": "OK",
  "parameters": {
      "id": 1378,
      "name": "Example",
      "url": "http://example.com/",
      "text": " Example Domain <p>This domain is for use in illustrative examples in documents.\nYou may use this domain in literature without prior coordination or asking for permission.</p>\n<p>More information...</p> ",
      "updated_at": "2020-12-14T22:20:50.860Z",
      "created_at": "2019-05-18T21:01:08.897Z",
      "text_version": null,
      "service_id": "502"
    }
}
```
