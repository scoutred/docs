---
date: 2017-01-26T19:56:50+01:00
title: Addresses
weight: 20
---

## /api/search/addresses

The `/api/search/addresses` endpoint will suggest addresses based on a provided query string. Also works with Assessor Parcel Numbers (APNs).

### HTTP Endpiont

`https://scoutred.com/api/search/addresses`

### Query string params

* `q` - The search query

### Example Request

```bash
# GET address suggestions based on the supplied query
$ curl -H "Authorization: Bearer [token]" \ 
	-XGET https://scoutred.com/api/search/addresses?q=1043
```

### Example Response
```json
[
	{
		"id": 843970,
		"parcelId": 1018057,
		"apn": "5353442062",
		"apnFmt": "535-344-20-62",
		"full": "207 Fifth Ave #1043",
		"street": {
			"number": 207,
			"numberFraction": null,
			"preDirection": null,
			"name": "FIFTH",
			"suffix": "AVE",
			"postDirection": null
		},
		"unit": "1043",
		"postal": "92101",
		"jurisdiction": "San Diego",
		"state": "CA",
		"country": "USA",
		"created": "2016-05-04T03:33:51.077522Z",
		"updated": "2016-07-11T23:24:34.965674Z"
	}
]
```