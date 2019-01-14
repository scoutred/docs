---
date: 2018-12-23T19:56:50+01:00
title: Zoning
---

## /api/zoning

The `/api/zoning` endpoint allows for querying all the zoning records using query string combinations.

### HTTP Endpoint

`https://scoutred.com/api/zoning`

### Query String Parameters

* `lon` - The longitude value to combine with the `lat` query string.
* `lat` - The latitude value to combine with the `lon` query string.

### Example Request

```bash
# GET parcels based on supplied lattitude and longitude values
$ curl -H "Authorization: Bearer [token]" \
    -XGET https://scoutred.com/api/zoning?lat=32.952645&lon=-117.235974
```

## /api/zoning/:id

The `/api/zoning/:id` endpoint will return zoning data using the a Scoutred zoning ID.

### HTTP Endpoint

`https://scoutred.com/api/zoning/:id`

### URL params

* `:id` - The Scoutred zoning ID

### Example Request

```bash
# GET address suggestions based on the supplied query
$ curl -H "Authorization: Bearer [token]" \ 
    -XGET https://scoutred.com/api/zoning/210502
```


## Example Resource

```json
{
    "id": 173,
    "jurisdiction": {
        "id": 2,
        "name": "City of San Diego",
        "created": "2016-03-27T01:15:32.875962Z",
        "updated": "2016-03-27T01:15:32.875962Z"
    },
    "designation": "IS-1-1",
    "description": null,
    "regulations": [{
        "id": 114,
        "zoningId": 173,
        "lotSize": {
            "minArea": null,
            "maxArea": null,
            "minWidth": null,
            "minWidthCorner": null,
            "minFrontage": null,
            "minDepth": null
        },
        "density": {
            "sfDu": null,
            "sfDuNote": null
        },
        "heightLimit": {
            "max": null,
            "aboveEnclosedParking": null,
            "roofFlat": null,
            "roofPitched": null,
            "note": null
        },
        "far": {
            "base": 2,
            "min": null,
            "max": null,
            "residential": null,
            "commercial": null,
            "mixed": null,
            "note": null
        },
        "setbacks": {
            "frontMin": 10,
            "frontMinNote": null,
            "frontMax": null,
            "frontMaxNote": null,
            "interiorSide": null,
            "interiorSideNote": "5 / 0",
            "streetSide": 10,
            "streetSideNote": null,
            "rear": 15,
            "rearAlley": null,
            "rearNote": null,
            "generalNote": null
        },
        "lotCoverage": {
            "min": null,
            "max": null,
            "note": null
        }
    }],
    "created": "2016-03-27T01:20:38.188055Z",
    "updated": "2016-03-27T01:20:38.188055Z"
}
```