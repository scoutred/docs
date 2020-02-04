---
date: 2018-12-23
title: Community Plans
---

## /api/community-plans/:id

The `/api/community-plan/:id` endpoint will return data for a community plan using the community plan's Scoutred ID.

### HTTP Endpoint

`https://scoutred.com/api/community-plans/:id`

### URL params

* `:id` - The Scoutred overlay ID.

### Example Request

```bash
# GET address suggestions based on the supplied query
$ curl -H "Authorization: Bearer [token]" \ 
    -XGET https://scoutred.com/api/community-plans/210502
```


## Example Resource

```json
{
  "id": 2,
  "name": "SABRE SPRINGS",
  "description": "Nestled in foothills north of Scripps Ranch and south of Carmel Mountain Ranch, Sabre Springs is home to quiet neighborhoods, rolling hills, business parks and City facilities. On the eastern edge of the Los Peñasquitos Canyon Preserve and north of Miramar Lake, Sabre Springs offers many recreational opportunities to provide residents with the balanced quality of life San Diegans are proud to enjoy.",
  "references": [
    {
      "id": 2,
      "sourceId": 1,
      "layerId": 3,
      "description": "Community Plan (PDF)",
      "url": "https://sandiego.gov/some-pdf.pdf",
      "created": "2016-04-29T18:58:46.089268-07:00",
      "updated": "2016-05-02T11:04:35.11786-07:00"
    }
  ],
  "jurisdiction": {
    "id": 2,
    "name": "City of San Diego",
    "created": "2016-03-26T18:15:32.875962-07:00",
    "updated": "2016-03-26T18:15:32.875962-07:00"
  },
  "bounds": {
    "crs": {
      "type": "name",
      "properties": {
        "name": "EPSG:4326"
      }
    },
    "bbox": [-117.1058018435, 32.9350320533, -117.0667062873, 32.9649824275],
    "type": "Polygon",
    "coordinates": [
      [
        [-117.1058018435, 32.9350320533],
        [-117.1058018435, 32.9649824275],
        [-117.0667062873, 32.9649824275],
        [-117.0667062873, 32.9350320533],
        [-117.1058018435, 32.9350320533]
      ]
    ]
  },
  "geohash": "9mudqqkz2j832gtc5hx7",
  "created": "2016-04-29T18:58:46.089268-07:00",
  "updated": "2016-05-02T11:04:35.11786-07:00"
}
```

