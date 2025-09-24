# GET /case/v2

Use this interface to retrieve a specific case from our database in JSON, or to list all cases.

As a reference, cases are also listed at [https://edit.tosdr.org/cases/](https://edit.tosdr.org/cases/).

## Endpoint

```
https://api.tosdr.org/case/v2/
```

## Parameters

| Parameter | Type    | Description                                     |
| --------- | ------- | ----------------------------------------------- |
| id        | Integer | Case ID to retrieve. Omit the parameter to list all cases. |
| page      | Integer | Pagination number (defaults to `1`).            |

## Repository

[https://github.com/tosdr/API/tree/master/functions/Case/GET/v2](https://github.com/tosdr/API/tree/master/functions/Case/GET/v2)

## Implemented error codes

| Error                                   | HTTP status | Bitmask            |
| --------------------------------------- | ----------- | ------------------ |
| An invalid case id has been supplied    | 404         | `INVALID_PARAMETER` |

## Example response

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
