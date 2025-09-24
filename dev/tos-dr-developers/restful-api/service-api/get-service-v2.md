# GET /service/v2/

Use this interface to retrieve a list of all or specific services from our database in json.

As a reference, you can also manually browse or search our Services on [https://edit.tosdr.org/services](https://edit.tosdr.org/services)\


**Endpoint**

```
https://api.tosdr.org/service/v2/
```

\


#### Parameters <a href="#get-service-v2-parameters" id="get-service-v2-parameters"></a>

| Parameter | Type    | Description                                            |
| --------- | ------- | ------------------------------------------------------ |
| id        | Integer | Optional ID of the Service, omit to list all services. |
| page      | Integer | The pagination number. Note pages start at 1           |

#### Repository <a href="#get-service-v2-repository" id="get-service-v2-repository"></a>

#### [https://github.com/tosdr/API/tree/master/functions/Service/GET/v2](https://github.com/tosdr/API/tree/master/functions/Service/GET/v2)  <a href="#get-service-v2-https-github.com-tosdr-api-tree-master-functions-service-get-v2" id="get-service-v2-https-github.com-tosdr-api-tree-master-functions-service-get-v2"></a>

#### Implemented Error codes <a href="#get-service-v2-implementederrorcodes" id="get-service-v2-implementederrorcodes"></a>

| Error Code       |
| ---------------- |
| INVALID\_SERVICE |

### Dataset Explorer <a href="#get-service-v2-datasetexplorer" id="get-service-v2-datasetexplorer"></a>

**Specific Service**

```
{
	"error": 256,
	"message": "OK",
	"parameters": {
		"id": 353,
		"is_comprehensively_reviewed": false,
		"name": "Yammer",
		"updated_at": "2021-03-31T01:04:42.630Z",
		"created_at": "2018-05-08T12:19:43.120Z",
		"slug": "yammer",
		"rating": null,
		"urls": ["yammer.com"],
		"image": "https:\/\/s3.tosdr.org\/logos\/353.png",
		"documents": [],
		"points": [{
			"id": 2145,
			"title": "Yammer.com (Microsoft Enterprise Social Network solution)",
			"source": "https:\/\/groups.google.com\/forum#!topic\/tosdr\/Gw8zB2bMUoU",
			"status": "declined",
			"analysis": "Yammer.com (Microsoft Enterprise Social Network solution)",
			"created_at": "2018-05-15T09:12:15.999Z",
			"updated_at": "2021-02-06T03:50:33.404Z",
			"case": {
				"id": 235,
				"classification": "neutral",
				"weight": 0,
				"title": "none",
				"description": "Do not select this case, because points with this case will not show up on tosdr.org",
				"topic_id": 53
			},
			"quoteText": null,
			"document_id": null,
			"quoteStart": null,
			"quoteEnd": null
		}]
	}
}
```

**All Services**

```
{
	"error": 256,
	"message": "All services below",
	"parameters": {
		"_page": {
			"total": 7390,
			"current": 1,
			"start": 1,
			"end": 74
		},
		"services": [{
			"id": 440,
			"is_comprehensively_reviewed": false,
			"name": "pebble",
			"urls": ["pebble.com"],
			"updated_at": "2021-03-25T03:19:30.208Z",
			"created_at": "2018-05-08T12:19:44.833Z",
			"slug": "pebble",
			"rating": null
		}, {
			"id": 330,
			"is_comprehensively_reviewed": false,
			"name": "SeenThis",
			"urls": ["seenthis.net"],
			"updated_at": "2021-03-25T03:19:33.465Z",
			"created_at": "2018-03-05T08:40:47.818Z",
			"slug": "seenthis",
			"rating": null
		}
		...]
	}
}
```

\


***

\


\
