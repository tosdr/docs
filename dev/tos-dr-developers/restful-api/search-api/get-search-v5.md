# GET /search/v5

Endpoint to retrieve services with a query

\


\


**Endpoint**

```
https://api.tosdr.org/search/v5/
```

\


#### Parameters <a href="#get-search-v5-parameters" id="get-search-v5-parameters"></a>

| Parameter | Type   | Description       |
| --------- | ------ | ----------------- |
| query     | String | The search string |

#### Limits <a href="#get-search-v5-limits" id="get-search-v5-limits"></a>

The endpoint has some rate-limiting in place. If you require higher rate limits, please contact us under team@tosdr.org\
\
Dataset Explorer (?query=tosdr)

```
{
    "services": [
        {
            "id": 596,
            "is_comprehensively_reviewed": true,
            "urls": [
                "tosdr.org",
                "tosdr.community",
                "ybf3byfbutzozmau4elus7zm5feo3cqvy74er4qnxkgicbatzfq3qhqd.onion",
                "cphdgvjdcet6ctztiqxabspxqojhafygqtfcjztxxn5jfngizzsp7tqd.onion",
                "xkp3bueakhnea3hw4t4izybudyysnoc4jt746z7555mpv2w4p73ihhyd.onion",
                "6tc72lnilgt4dn2u6qk44vfns2qca552smajbilfcl6zs7ezf7emhbad.onion",
                "5qicbosngbkejsqpkywunvechlmcivsnhy2u5pbhtxd2laq5p7ufohid.onion"
            ],
            "name": "ToS;DR",
            "updated_at": "2023-11-17T18:01:03.518737",
            "created_at": "2018-07-09T08:24:52.683422",
            "slug": "tosdr",
            "rating": "B"
        },
        {
            "id": 969,
            "is_comprehensively_reviewed": true,
            "urls": [
                "edit.tosdr.org"
            ],
            "name": "ToS;DR Phoenix",
            "updated_at": "2021-05-14T14:37:48.921336",
            "created_at": "2018-12-21T00:57:18.464734",
            "slug": "tosdr_phoenix",
            "rating": "A"
        }
    ]
}
```

\


\


### Related articles <a href="#get-search-v5-relatedarticles" id="get-search-v5-relatedarticles"></a>

* Page:GET /search/v5
* Page:GET /search/v3
* Page:GET /search/v4

\


\


\
