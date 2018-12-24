---
date: 2017-01-26T19:56:50+01:00
title: Addresses
weight: 10
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

## Schema

| Name                  	| Type    	| Description                                                                 	|
|-----------------------	|---------	|-----------------------------------------------------------------------------	|
| id                    	| integer 	| Scoutred address ID                                                         	|
| parcelId              	| integer 	| The id of the parcel the address is associated with                         	|
| apn                   	| string  	| The unformatted Assessor Parcel Number (APN)                                	|
| apnFmt                	| string  	| The formatted Assessor Parcel Number (APN)                                  	|
| full                  	| string  	| A single line formatted version of the street attributes                    	|
| street                	| object  	| Various attributes which make up the street                                 	|
| street.number         	| integer 	| The street number                                                           	|
| street.numberFraction 	| string  	| The street number fraction if applicable                                    	|
| street.preDirection   	| string  	| The street pre direction (i.e. N, S, E, W) if applicable.                   	|
| street.name           	| string  	| The name of the street                                                      	|
| street.suffix         	| string  	| The string suffix (i.e. Ave, St, Dr.)                                       	|
| street.postDirection  	| string  	| The street pre direction (i.e. N, S, E, W) if applicable.                   	|
| unit                  	| string  	| The address unit. Applicable to condos.                                     	|
| postal                	| string  	| The postal (zip) code for the address.                                      	|
| jurisdiction          	| string  	| The jurisdiction for the address                                            	|
| state                 	| string  	| The two letter representation of the state the address resides in (i.e. CA) 	|
| country               	| string  	| The country the address resides in (i.e. USA)                               	|
| created               	| string  	| A RFC3339 timestamp for record creation.                                    	|
| modified              	| string  	| A RFC3339 timestamp for record modification.                                	|