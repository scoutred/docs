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
    "id": 48,
    "name": "MIDWAY-PACIFIC HIGHWAY",
    "description": "The Midway/Pacific Highway Corridor Community (e.g. Midway) is situated north of the Centre City ...",
    "references": null,
    "created": "2016-04-30T01:58:46.089268Z",
    "updated": "2016-05-08T20:52:41.756657Z"
}
```

