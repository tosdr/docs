# GET /search/v3

Retrieve services with ElasticSearch queries. This version only supports the `query` parameter and has been superseded by `GET /search/v4`.

## Endpoint

```
https://api.tosdr.org/search/v3/
```

## Parameters

| Parameter | Type   | Description       |
| --------- | ------ | ----------------- |
| query     | String | The search string |

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
| WIP          |

## JSON schema

`WIP`
