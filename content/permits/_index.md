---
date: 2019-05-14T19:56:50+01:00
title: Permits
---

## /api/search/permits

The `/api/search/permits` endpoint will suggest permits based on a provided query string. Also works with Assessor Parcel Numbers (APNs).

### HTTP Endpoint

`https://scoutred.com/api/search/permits`

### Query string params

* `q` - The search query
* `bbox` - A bounding box to filter the results set by. The values are comma seperated with the first two values designating SouthWest and the second two designating NorthEast.

### Example Request

```bash
# GET address suggestions based on the supplied query
$ curl -H "Authorization: Bearer [token]" \ 
    -XGET https://scoutred.com/api/search/permit?q=1043&bbox=32.73766608197677,-117.12972546369107,32.74250765848572,-117.12734902650817
```

### Example Response
```javascript
{
    "hits": 216,
    "permits": [...permit resource...]
}
```


## /api/permits/:id

The `/api/permits/:id` endpoint will return data for a permit using the permit's Scoutred permit ID.

### HTTP Endpoint

`https://scoutred.com/api/permits/:id`

### URL params

* `:id` - The permit's Scoutred permit ID.

### Example Request

```bash
# GET address suggestions based on the supplied query
$ curl -H "Authorization: Bearer [token]" \ 
    -XGET https://scoutred.com/api/permits/6669986
```


## Example Resource

```javascript
{
    "id": 6669986,
    "parcelId": 362266,
    "jurisdiction": {
        "id": 2,
        "name": "City of San Diego",
        "created": null,
        "updated": null
    },
    "jurisdictionPermitId": "2236098",
    "description": "New pool \u0026 spa per MP #525633 for extg sdu. ",
    "appliedDate": "2018-12-20T00:00:00Z",
    "issueDate": "2019-01-30T00:00:00Z",
    "completedDate": "0001-01-01T00:00:00Z",
    "originalAddress1": "3352 31ST ST ",
    "originalAddress2": null,
    "originalCity": null,
    "originalState": null,
    "originalZip": null,
    "classRaw": null,
    "classMapped": null,
    "statusCurrentRaw": "Pending Invoice Payment",
    "statusCurrentId": null,
    "workClass": null,
    "workClassMapped": null,
    "typeRaw": "Combination Building Permit",
    "typeId": null,
    "typeDescription": null,
    "statusDate": null,
    "totalSf": null,
    "link": null,
    "estimatedProjectCost": null,
    "housingUnits": 0,
    "apn": "4534922500",
    "proposedUse": null,
    "addedSf": null,
    "removedSf": null,
    "masterPermitNumber": null,
    "expiredDate": null,
    "coIssueDate": null,
    "holdDate": null,
    "voidDate": null,
    "projectName": "Penick Pool \u0026 Spa",
    "projectId": "625629",
    "totalFinishedSf": null,
    "totalUnfinishedSf": null,
    "totalHeatedSf": null,
    "totalUnheatedSf": null,
    "totalAccessorySf": null,
    "totalSprinkledSf": null,
    "extraFields": null,
    "publisher": "OpenDSD",
    "fee": 29260,
    "contractor": {
        "id": null,
        "licenseNumber": null,
        "licenseState": null,
        "fullName": null,
        "companyName": null,
        "companyDescription": null,
        "phone": null,
        "address1": null,
        "address2": null,
        "city": null,
        "state": null,
        "zip": null,
        "email": null,
        "trade": {
            "id": null,
            "name": null,
            "updated": null,
            "created": null
        },
        "created": null,
        "updated": null
    },
    "geom": {
        "crs": {
            "type": "name",
            "properties": {
                "name": "EPSG:4326"
            }
        },
        "type": "Point",
        "coordinates": [-117.127451, 32.740236]
    },
    "created": "2018-12-26T00:01:39.334938Z",
    "updated": "2018-12-26T00:01:39.334938Z"
}
```