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
    -XGET https://scoutred.com/api/overlays/210502
```

## Example Resource

```json
{
    "id": 58,
    "name": "Coastal Height Limit Overlay Zone",
    "designation": "CHLOZ",
    "ordinance": "O-10960 NS",
    "implementationDate": "1972-12-07T00:00:00Z",
    "jurisdiction": {
        "id": 2,
        "name": "City of San Diego",
        "created": "2016-03-27T01:15:32.875962Z",
        "updated": "2016-03-27T01:15:32.875962Z"
    },
    "description": "The purpose of the Coastal Height Limit Overlay Zone is to provide a supplemental ...",
    "created": "2016-05-09T01:21:19.123113Z",
    "updated": "2016-05-09T02:11:56.356377Z"
}
```