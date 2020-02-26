---
date: 2018-12-23T19:56:50+01:00
title: Parcels
---

## /api/parcels

The `/api/parcels` allows for querying all the parcels in the system using query string combinations. All responses will be wrapped in an array as more than one record can be returned.

### HTTP Endpoint

`https://scoutred.com/api/parcels`

The endpoint provides a way to query for parcels using various parameters. The response will always be an array of 0 or more parcel resources.

### Query String Parameters

* `lon` - The longitude value to combine with the `lat` query string.
* `lat` - The latitude value to combine with the `lon` query string.

### Example Request

```bash
# GET parcels based on supplied latitude and longitude values
$ curl -H "Authorization: Bearer [token]" \
    -XGET 'https://scoutred.com/api/parcels?lat=32.952645&lon=-117.235974'
```

## /api/parcels/:id

The `/api/parcels/:id` endpoint will return data for a parcel using the parcel's Scoutred parcel ID.

### HTTP Endpoint

`https://scoutred.com/api/parcels/:id`

### URL parameters

* `:id` - The parcel's Scoutred parcel ID. The ID can be obtained using the [Address Search API](/addresses/#api-search-addresses).

### Query parameters

* `address_id` - The ID of the address to return as the parcel's address. This is useful when a parcel has more than a single address associated with it and an user found the address via the Address Search API. The value for `address_id` is the `id` field returned by the [Address Search API](/addresses/#api-search-addresses).

### Example Request

```bash
$ curl -H "Authorization: Bearer [token]" \ 
	-XGET https://scoutred.com/api/parcels/210502
```


## /api/parcels/:id/dimensions

The endpoint will return GeoJSON of the parcel's lot line dimensions. The response GeoJSON will be a FeatureCollection with an individual feature for each parcel lot line segment. Each feature's `properties` object contains the key `lineLengthFt` which contains the length of the line segment in feet.

**Note**: This endpoint is experimental. Parcel line segments may have undesirable values. Please use with caution. 

### HTTP Endpoint

`https://scoutred.com/api/parcels/:id/dimensions`

### URL parameters

* `:id` - The parcel's Scoutred parcel ID. The ID can be obtained using the [Address Search API](/addresses/#api-search-addresses).

### Example Request

```bash
$ curl -H "Authorization: Bearer [token]" \
    -XGET https://scoutred.com/api/parcels/210502/dimensions
```

### Example Response

```javascript
{
  "type": "FeatureCollection",
  "features": [
    {
      "type": "Feature",
      "geometry": {
        "type": "LineString",
        "coordinates": [
          [
            -117.14405,
            32.743459
          ],
          [
            -117.144261,
            32.743455
          ]
        ]
      },
      "properties": {
        "lengthFt": 65.06,
        "unlocked": true // if false lengthFt is redacted
      }
    },
    {
      "type": "Feature",
      "geometry": {
        "type": "LineString",
        "coordinates": [
          [-117.144261, 32.743455],
          [-117.144261, 32.743483]
        ]
      },
      "properties": {
        "lengthFt": -1.0,
        "unlocked": false // if false lengthFt is redacted
      }
    }
  ]
}

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
        "name1": "LOCKED",
        "name2": "LOCKED",
        "name3": "LOCKED",
        "address1": "LOCKED",
        "address2": "LOCKED",
        "address3": "LOCKED",
        "address4": "LOCKED",
        "postal": "LOCKED"  
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
   "lotSizeSF" : 1231,   // the lot size in square feet
   "lotSizeAcre": 0.028, // the lot size in acre
   "geomArea": 1231.0,   // area of the geometry in square feet (deprecated, use lotSizeSF)
   "communityPlan": {...communityPlan resource...},
   "zoning": [...zoning resources...],
   "overlays": [... overlays resources...],
   "permits": [... permits resource ...]
   "bounds": {
      "type": "Polygon",
      "coordinates": [
         [
            [-117.180183060805, 32.6963180459813],
            [-117.180183060805, 32.7305263087481],
            [-117.147086641189, 32.7305263087481],
            [-117.147086641189, 32.6963180459813],
            [-117.180183060805, 32.6963180459813]
         ]
      ]
   },
   "geohash" : "",
   "created": "2016-05-04T03:33:51.077522Z",
   "updated": "2016-07-11T23:24:34.965674Z",
   "unlocked": false, // if false owner information is redacted
   "collection": [... collecitons resource ...]
}
```
