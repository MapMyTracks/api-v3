Get routes
=========
Get a user's routes from Map My Tracks

Parameters
---
None

Response
---

If the call was successful then a HTTP response code of 200 will be returned. If the user who made the request has routes then then the API will return a JSON formatted reply with relevant data for each route found.

If the user who made the request has no results, then a JSON formatted reply indicating that this is the case will be returned.

If the call was made by an unauthorised user then a HTTP response code of 401 will be returned.

Example
---

````
curl -H 'Authorization: Bearer <access_token>' 'https://routes.mapmytracks.com/api/get_routes'
````

**Results:**
````
[
{
"title": "Mont Ventoux (Bédoin)",
"created_at": 1713179624,
"modified_at": null,
"distance": "21353.009197749554",
"elevation_gain": "1549.61",
"elevation_loss": "1.776",
"elevation_max": "1869.72",
"elevation_min": "1862.37",
"duration": "5463.8891686247225",
"activity": "road-bike",
"route_id": "wdn11rcb0b1iskjhdoijed3zzhcb1dwjef5m52ca96j1"
},
{
"title": "Col du Tourmalet",
"created_at": 1713528404,
"modified_at": null,
"distance": "17053.273",
"elevation_gain": "1242.214",
"elevation_loss": "0.73000000000025",
"elevation_max": "2116.87",
"elevation_min": "855.05",
"duration": "5025.219",
"activity": "road-bike",
"route_id": "ja2aq8x587rfluduigsbjeh1s9ju2jeainfd6a7iq"
},
]
````

**Without results:**
````
{
"error": "No routes available"
}
````
