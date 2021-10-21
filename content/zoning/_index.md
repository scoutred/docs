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
    -XGET https://scoutred.com/api/zoning/183
```


## Example Resource

```json
{
    "id": 183,
    "jurisdiction": {
        "id": 2,
        "name": "City of San Diego",
        "created": "2016-03-27T01:15:32.875962Z",
        "updated": "2016-03-27T01:15:32.875962Z"
    },
    "designation": "RM-1-1",
    "description": "The purpose of the RM zones is to provide for multiple dwelling unit development at varying densities. The RM zones individually accommodate developments with similar densities and characteristics. Each of the RM zones is intended to establish development criteria that consolidates common development regulations, accommodates specific dwelling types, and responds to locational issues regarding adjacent land uses.",
    "bounds": {
        "crs": {
            "type": "name",
            "properties": {
                "name": "EPSG:4326"
            }
        },
        "bbox": [
            -117.28151,
            32.54543,
            -117.00632,
            33.05589
        ],
        "type": "Polygon",
        "coordinates": [
            [
                [
                    -117.28151,
                    32.54543
                ],
                [
                    -117.28151,
                    33.05589
                ],
                [
                    -117.00632,
                    33.05589
                ],
                [
                    -117.00632,
                    32.54543
                ],
                [
                    -117.28151,
                    32.54543
                ]
            ]
        ]
    },
    "use": {
        "primary": "residential",
        "secondary": "multi family"
    },
    "geohash": "9mudw74msyxf3jew8kbu",
    "regulations": [{
        "id": 187,
        "zoningId": 183,
        "lotSize": {
            "minArea": null,
            "maxArea": null,
            "minWidth": null,
            "minWidthCorner": null,
            "minFrontage": null,
            "minDepth": null
        },
        "density": {
            "sfDu": 3000,
            "sfDuNote": null
        },
        "heightLimit": {
            "max": 30,
            "aboveEnclosedParking": null,
            "roofFlat": null,
            "roofPitched": null,
            "note": null
        },
        "far": {
            "base": 0.75,
            "min": null,
            "max": null,
            "residential": null,
            "commercial": null,
            "mixed": null,
            "note": null
        },
        "setbacks": {
            "frontMin": 15,
            "frontMinNote": null,
            "frontMax": null,
            "frontMaxNote": null,
            "interiorSide": 5,
            "interiorSideNote": null,
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
    "references": [
        {
            "id": 366,
            "zoningId": 183,
            "description": "Municipal Code (PDF)",
            "url": "http://docs.sandiego.gov/municode/MuniCodeChapter13/Ch13Art01Division04.pdf",
            "created": "2016-05-11T05:23:39.337241Z",
            "updated": "2016-05-11T05:23:39.337241Z"
        }
    ],
    "created": "2016-03-27T01:20:38.188055Z",
    "updated": "2021-05-02T13:42:54.574751Z"
}
```

## Data Schema

| Name                      | Type      | Description                                                                          |
|-----------------------    |---------  |-----------------------------------------------------------------------------------   |
| id                        | integer   | Scoutred resource ID                                                                 |
| name                      | string    | Display name of the layer.                                                           |
| jurisdiction              | object    | The Jurisdiction that administer's the overlay.                                      |
| designation               | string    | The Jurisdiction's zoning designation code                                           |
| bounds                    | geojson   | A geoJSON object for the bounding box of the overlay.                                |
| geohash                   | string    | A geohash of the overlay.                                                            |
| use                       | object    | Describes the primary and secondary uses for of the zoning. These are normalized values across jurisdictions.|
| use.primary               | string    | Can be one of: `commercial`, `industrial`, `mixed use`, `open space`, `planned district`, `residential`, `government`, `agriculture`, `parking`. |
| use.secondary             | string    | A sub attribute under `use.primary`. For exmple, `residential` will be either `single family` or `multi family`. This field is not currently stable and should not be relied on. |
| regulations               | array     | An array of various land used regulations (i.e. height limits, lot coverage, setbacks, etc.)
| references                | array     | An array of reference links associated with the overlay.                             |
| created                   | string    | A RFC3339 timestamp for record creation.                                             |
| updated                   | string    | A RFC3339 timestamp for record modification.                                         |
