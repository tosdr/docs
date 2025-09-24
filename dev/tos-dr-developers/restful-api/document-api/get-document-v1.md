# GET /document/v1

Use this interface to retrieve a Document from our database.

**Endpoint**

```
https://api.tosdr.org/document/v1
```

#### Parameters <a href="#get-document-v1-parameters" id="get-document-v1-parameters"></a>

| Parameter | Type    | Description                                                              |
| --------- | ------- | ------------------------------------------------------------------------ |
| id        | Integer | The Doc ID to retrieve. Omit to list all document IDs and text\_versions |

#### &#x20;Repository <a href="#get-document-v1-repository" id="get-document-v1-repository"></a>

[https://github.com/tosdr/API/tree/master/functions/public/Document/GET/v1](https://github.com/tosdr/API/tree/master/functions/public/Document/GET/v1)

#### Implemented Error codes <a href="#get-document-v1-implementederrorcodes" id="get-document-v1-implementederrorcodes"></a>

| **Error**                           | **HTTP Status** | **Bitmask**         |
| ----------------------------------- | --------------- | ------------------- |
| An invalid doc id has been supplied | 404             | `INVALID_PARAMETER` |

**Example response**

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

### Related articles <a href="#get-document-v1-relatedarticles" id="get-document-v1-relatedarticles"></a>

* Page:GET /search/v5
* Page:GET /search/v3
* Page:GET /search/v4
