# GET /search/v4

Use this endpoint to retrieve services with a query.

## Endpoint

```
https://api.tosdr.org/search/v4/
```

## Parameters

| Parameter | Type   | Description       |
| --------- | ------ | ----------------- |
| query     | String | The search string |

## Global rate limit

This interface applies the shared platform rate limits shown below. Individual endpoints may define additional limits.

| Benefit | Second | Hour   | Day    |
| ------- | ------ | ------ | ------ |
| Guest   | 15     | 1000   | 15000  |
| Staff   | 15000  | 100000 | 150000 |
| Office  | 15000  | 100000 | 150000 |
| Partner | 150    | 10000  | 50000  |

## Implemented error codes

| Error code    |
| ------------- |
| QUERY_FAILED  |
