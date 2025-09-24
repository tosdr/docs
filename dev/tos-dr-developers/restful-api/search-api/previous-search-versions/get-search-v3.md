# GET /search/v3

Endpoint to retrieve services with ElasticSearch queries. (Currently only supports the query parameter)

This API has been superseded by **GET /search/v4/**

\


**Endpoint**

```
https://api.tosdr.org/search/v3/
```

\


#### Parameters <a href="#get-search-v3-parameters" id="get-search-v3-parameters"></a>

| Parameter | Type   | Description       |
| --------- | ------ | ----------------- |
| query     | String | The search string |

\


#### Global Rate Limit <a href="#get-search-v3-globalratelimit" id="get-search-v3-globalratelimit"></a>

| Benefit | Second | Hour   | Day    |
| ------- | ------ | ------ | ------ |
| Guest   | 15     | 1000   | 15000  |
| Staff   | 15000  | 100000 | 150000 |
| Office  | 15000  | 100000 | 150000 |
| Partner | 150    | 10000  | 50000  |

This rate limit applies to all interfaces. Each Interface and method may implement its own rate limit.

\


#### Implemented Error codes <a href="#get-search-v3-implementederrorcodes" id="get-search-v3-implementederrorcodes"></a>

| Error Code    |
| ------------- |
| QUERY\_FAILED |
| WIP           |

\


\


**JSON Schema**

```
WIP
```

### Related articles <a href="#get-search-v3-relatedarticles" id="get-search-v3-relatedarticles"></a>

* Page:GET /search/v5
* Page:GET /search/v3
* Page:GET /search/v4

\


\


\
