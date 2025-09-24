# GET /case/v2

Use this interface to retrieve a specific case from our database in json. Or, a list of all cases.

As a reference, a list of Cases is also listed here: [https://edit.tosdr.org/cases/](https://edit.tosdr.org/cases/)\


**Endpoint**

```
https://api.tosdr.org/case/v2/
```

#### Parameters <a href="#get-case-v2-parameters" id="get-case-v2-parameters"></a>

| Parameter | Type    | Description                                     |
| --------- | ------- | ----------------------------------------------- |
| id        | Integer | The Case ID to retrieve. Omit to list all cases |
| page      | Integer | The pagination number. Default 1                |

#### &#x20;Repository <a href="#get-case-v2-repository" id="get-case-v2-repository"></a>

[https://github.com/tosdr/API/tree/master/functions/Case/GET/v2](https://github.com/tosdr/API/tree/master/functions/Case/GET/v2)

#### Implemented Error codes <a href="#get-case-v2-implementederrorcodes" id="get-case-v2-implementederrorcodes"></a>

| **Error**                            | **HTTP Status** | **Bitmask**         |
| ------------------------------------ | --------------- | ------------------- |
| An invalid case id has been supplied | 404             | `INVALID_PARAMETER` |

**Example response**

```
{
  "error": 256,
  "message": "OK",
  "parameters": {
      "id": 122,
      "weight": 0,
      "title": "The terms may be changed at any time, but you will receive notification of the changes",
      "description": "The Terms may be updated without prior notice, but users will be notified of the changes at the moment they will start applying.",
      "updated_at": "2021-05-07T16:23:11.148Z",
      "created_at": "2018-01-16T15:26:08.192Z",
      "topic_id": 46,
      "classification": "neutral"
    }
}
```

### Related articles <a href="#get-case-v2-relatedarticles" id="get-case-v2-relatedarticles"></a>

* Page:GET /search/v5
* Page:GET /search/v3
* Page:GET /search/v4
