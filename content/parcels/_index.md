---
date: 2018-12-23T19:56:50+01:00
title: Parcels
---

## /api/parcels

The `/api/parcels` allows for querying all the parcels in the system using query string combinations. All responses will be wrapped in an array as more than one record can be returned.

### HTTP Endpoint

`https://scoutred.com/api/parcels`

### Query String Parameters

* `lon` - The longitude value to combine with the `lat` query string.
* `lat` - The latitude value to combine with the `lon` query string.

### Example Request

```bash
# GET parcels based on supplied lattitude and longitude values
$ curl -H "Authorization: Bearer [token]" \
    -XGET 'https://scoutred.com/api/parcels?lat=32.952645&lon=-117.235974'
```

## /api/parcels/:id

The `/api/parcels/:id` endpoint will return data for a parcel using the parcel's Scoutred parcel ID.

### HTTP Endpoint

`https://scoutred.com/api/parcels/:id`

### URL params

* `:id` - The parcel's Scoutred parcel ID. The ID can be obtained using the [Address Search API](/addresses/#api-search-addresses).

### Example Request

```bash
# GET address suggestions based on the supplied query
$ curl -H "Authorization: Bearer [token]" \ 
	-XGET https://scoutred.com/api/parcels/210502
```


## Example Resource

```javascript
{
    "id": 210502,
    "stateFIPS": "06",
    "countyFIPS": "073",
    "apn": "4415811100",
    "address": {
        "id": 574404,
        "parcelId": 210502,
        "street": {
            "number": 3460,
            "numberFraction": null,
            "preDirection": null,
            "name": "HANCOCK",
            "suffix": "ST",
            "postDirection": null
        },
        "unit": null,
        "postal": "92110",
        "jurisdiction": "San Diego",
        "state": "CA",
        "country": "USA",
        "geom": {
            "crs": {
                "type": "name",
                "properties": {
                    "name": "EPSG:4326"
                }
            },
            "type": "Point",
            "coordinates": [-117.208274119352, 32.7564461631081]
        },
        "created": "2016-05-04T03:33:51.077522Z",
        "updated": "2016-07-11T23:24:34.965674Z"
    },
    "owner": {
        "name1": "REDACTED",
        "name2": null,
        "name3": null,
        "address1": "REDACTED",
        "address2": "REDACTED",
        "address3": null,
        "address4": null,
        "postal": "REDACTED"  
    },
    "legalDescription": "BLK 1*",
    "subdivision": {
        "name": "ASCHOFF MILLER \u0026 KELLYS SUB",
        "map": "000578"
    },
    "assessor": {
        "land": 176769,
        "improvements": 91918
    },
    "structure":{
        "effectiveYearBuilt": 1908,
        "livingSF": 1036,
        "usableSF": 6200,
        "units": 1,
        "bedrooms": 3,
        "bathrooms": 2
    },
    "geomArea": 1231.12, // area of the geometry in square feet
    "communityPlan": {...communityPlan resource...},
    "zoning": [...zoning resources...],
    "overlays": [... overlays resources...],
    "permits": [... permits resource ...]
}
```