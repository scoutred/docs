---
date: 2018-12-23
title: Overlays
---

## /api/overlays/:id

The `/api/overlays/:id` endpoint will return data for an overlay using the overlays's Scoutred ID.

### HTTP Endpoint

`https://scoutred.com/api/overlays/:id`

### URL params

* `:id` - The Scoutred overlay ID.

### Example Request

```bash
# GET address suggestions based on the supplied query
$ curl -H "Authorization: Bearer [token]" \ 
    -XGET https://scoutred.com/api/overlays/19353
```

## Example Resource

```json
{
    "id": 19353,
    "name": "Coastal Height Limit Overlay Zone",
    "jurisdiction": {
        "id": 2,
        "name": "City of San Diego",
        "created": "2016-03-27T01:15:32.875962Z",
        "updated": "2016-03-27T01:15:32.875962Z"
    },
    "description": "The purpose of the Coastal Height Limit Overlay Zone is to provide a supplemental height limit for specific coastal areas as enacted by the voters of the City of San Diego.",
    "category": "regulatory",
    "details": [
        {
            "name": "Designation",
            "value": "CHLOZ"
        }, 
        {
            "name": "Ordinance",
            "value": "O-10960 NS"
        },
        {
            "name": "Implementation Date",
            "value": "1972-12-07"
        }
    ],
    "bounds": {
        "crs": {
            "type": "name",
            "properties": {
                "name": "EPSG:4326"
            }
        },
        "bbox": [-117.2823414129, 32.6648118453, -117.1705745229, 32.9820691877],
        "type": "Polygon",
        "coordinates": [
            [
                [-117.2823414129, 32.6648118453],
                [-117.2823414129, 32.9820691877],
                [-117.1705745229, 32.9820691877],
                [-117.1705745229, 32.6648118453],
                [-117.2823414129, 32.6648118453]
            ]
        ]
    },
    "geohash": "9mudsrq63sc92h2qg1m9",
    "references": [{
        "id": 3,
        "sourceId": 2,
        "layerId": 5,
        "description": "Municipal Code (PDF)",
        "url": "http://docs.sandiego.gov/municode/MuniCodeChapter13/Ch13Art02Division05.pdf",
        "created": "2018-06-25T05:55:25.581175Z",
        "updated": "2018-06-25T05:55:25.581175Z"
    }],
    "created": "2018-06-26T13:58:06.149176Z",
    "updated": "2019-01-04T15:01:18.431281Z"
}
```


## Data Schema

| Name                      | Type      | Description                                                                          |
|-----------------------    |---------  |-----------------------------------------------------------------------------------   |
| id                        | integer   | Scoutred resource ID                                                                 |
| name                      | string    | Display name of the layer.                                                           |
| jurisdiction              | object    | The Jurisdiction that administer's the overlay.                                      |
| description               | string    | A description of the overaly.                                                        |
| category                  | string    | A category of the overlay. Can be one of: `aviation`, `ecological`, `transportation`, `historical`, `hazard`, `regulatory`, `economic`.|
| details                   | array     | An array of objects with attributes about the overlay.                               |
| bounds                    | geojson   | A geoJSON object for the bounding box of the overlay.                                |
| geohash                   | string    | A geohash of the overlay.                                                            |
| references                | array     | An array of reference links associated with the overlay.                             |
| country                   | string    | The country the address resides in (i.e. USA)                                        |
| created                   | string    | A RFC3339 timestamp for record creation.                                             |
| updated                   | string    | A RFC3339 timestamp for record modification.                                         |
