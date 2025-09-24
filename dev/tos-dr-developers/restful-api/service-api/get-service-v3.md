# GET /service/v3/

Use this interface to retrieve a specific service from our database in JSON format.

As a reference, you can also manually browse or search services at [https://edit.tosdr.org/services](https://edit.tosdr.org/services).

## Endpoint

```
https://api.tosdr.org/service/v3/
```

## Parameters

| Parameter | Type    | Description                                                                                                                                                        |
| --------- | ------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| id        | Integer | ID of the service.                                                                                                                                                 |
| lang      | String  | Optional 2-letter language code (`de`, `nl`, `fr`, `es`). If omitted, no localized titles are loaded and all `localized_title` fields remain `null`. |

## Example response

### Specific service

```
{
    "id": 596,
    "is_comprehensively_reviewed": true,
    "name": "ToS;DR",
    "updated_at": "2023-11-17T18:01:03.518737",
    "created_at": "2018-07-09T08:24:52.683422",
    "slug": "tosdr",
    "rating": "B",
    "urls": [
        "tosdr.org",
        "tosdr.community"
    ],
    "image": "https://s3.tosdr.org/logos/596.png",
    "documents": [
        {
            "id": 1269,
            "name": "Terms of Contribution",
            "url": "https://docs.tosdr.org/sp/tosdr-org-terms-of-contribution",
            "updated_at": "2024-11-08T11:35:59.829096",
            "created_at": "2019-05-11T22:55:02.368371"
        },
        ...
    ],
    "points": [
        {
            "id": 4523,
            "title": "The terms for ToS;DR are easy to read",
            "source": "https://edit.tosdr.org/about#tos",
            "status": "approved",
            "analysis": "Altogether, ToS and PP only make up eight lines of text.",
            "case": {
                "id": 199,
                "weight": 15,
                "title": "The terms for this service are easy to read",
                "localized_title": null,
                "description": "The Agreements are well-organised, define legal terms (where applicable), aren't needlessly long and may be pleasant to read.",
                "updated_at": "2021-05-14T12:47:00.376324",
                "created_at": "2018-01-16T15:26:09.875993",
                "topic_id": 36,
                "classification": "good"
            },
            "document_id": null,
            "updated_at": "2018-08-27T08:20:58.063021",
            "created_at": "2018-08-24T04:32:06.765518"
        },
        ...
    ]
}
```
