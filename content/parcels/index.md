---
date: 2017-01-26T19:56:50+01:00
title: Parcels
weight: 30
---

## /api/parcels/:id

The `/api/parcels/:id` endpoint will return data for a parcel using the parcel's ScoutRED parcel ID.

### HTTP Endpiont

`https://scoutred.com/api/parcels/:id`

### URL params

* `:id` - The parcel's ScoutRED parcel ID. The ID can be obtained using the Address Search API.

### Example Request

```bash
# GET address suggestions based on the supplied query
$ curl -H "Authorization: Bearer [token]" \ 
	-XGET https://scoutred.com/api/parcels/210502
```

### Example Response

```json
{
	"id": 210502,
	"stateFIPS": "06",
	"countyFIPS": "073",
	"apn": "4415811100",
	"owner": {
		"name1": "REDACTED",
		"name2": null,
		"name3": null,
		"address1": "REDACTED",
		"address2": "REDACTED",
		"address3": null,
		"address4": null,
		"postal": "REDACTED" // 
	},
	"legalDescription": "BLK 1*",
	"subdivision": {
		"name": "000578",
		"map": "ASCHOFF MILLER \u0026 KELLYS SUB"
	},
	"assessor": {
		"land": 176769,
		"improvements": 91918
	},
	"communityPlan": {
		"id": 48,
		"name": "MIDWAY-PACIFIC HIGHWAY",
		"description": "The Midway/Pacific Highway Corridor Community (e.g. Midway) is situated north of the Centre City ...",
		"references": null,
		"created": "2016-04-30T01:58:46.089268Z",
		"updated": "2016-05-08T20:52:41.756657Z"
	},
	"zoning": [{
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
	}],
	"overlays": [{
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
	}, {
		"id": 148,
		"name": "Airport Influence Area",
		"designation": "San Diego International Airport",
		"ordinance": null,
		"implementationDate": null,
		"jurisdiction": {
			"id": 2,
			"name": "City of San Diego",
			"created": "2016-03-27T01:15:32.875962Z",
			"updated": "2016-03-27T01:15:32.875962Z"
		},
		"description": null,
		"created": "2016-05-09T01:43:16.495715Z",
		"updated": "2016-05-09T01:43:16.495715Z"
	}]
}
```