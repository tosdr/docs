# GET /search/v5

Use this endpoint to retrieve services that match a query.

## Endpoint

```
https://api.tosdr.org/search/v5/
```

## Parameters

| Parameter | Type   | Description       |
| --------- | ------ | ----------------- |
| query     | String | The search string |

## Rate limiting

The endpoint is rate limited. For higher limits, contact the team at `team@tosdr.org`.

## Example response

`GET /search/v5?query=tosdr`

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
