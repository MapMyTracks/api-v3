Get route data
====
Get route data from a user's individual route.

Parameters
---
- `route_uid` *(required)*
The identifier used to find the correct route.

Response
---

If the call was successful, the API returns with a HTTP response code of 200. If route_uid provided has and associated route and the user has access to it that a JSON formatted response will be returned with relevant top level route information as well as a list of all the routes coordinates and pois.

If there is no associated route or the user does not have access to it then a JSON formatted error message will be returned stating that there is no data available.

If the call was made by an unauthorised user then a HTTP response code of 401 will be returned.

Examples
---

````
curl -H 'Authorization: Bearer <access_token>' 'https://routes.mapmytracks.com/api/get_route_data?route_uid=<route_uid>'
````

**Results**
````
{
"title": "London to Brighton",
"created_at": 1718279495,
"modified_at": null,
"distance": "73268.648",
"elevation_gain": "544",
"elevation_loss": "543",
"elevation_max": "61.17",
"elevation_min": "1.16",
"duration": "13516.807999999997",
"activity": "road-bike",
"route_id": "1lv5exxoryesw71rxdfgrdfgrt5dlee230fsjbo",
"coords": [
{
"lat": 51.28258,
"lng": 1.080466,
"elevation": 10.16,
"road_type": "Street",
"surface_type": "Asphalt",
"distance_in_route": 0
},
{
"lat": 51.282579,
"lng": 1.080478,
"elevation": 10.16,
"road_type": "Street",
"surface_type": "Asphalt",
"distance_in_route": 0.84226263558104
},
{
"lat": 51.282575,
"lng": 1.080564,
"elevation": 10.17,
"road_type": "Street",
"surface_type": "Asphalt",
"distance_in_route": 6.8421284394506
},
{
"lat": 51.28257,
"lng": 1.080709,
"elevation": 10.17,
"road_type": "Street",
"surface_type": "Asphalt",
"distance_in_route": 16.945647697904
},
{
"lat": 51.28257,
"lng": 1.081384,
"elevation": 10.25,
"road_type": "Street",
"surface_type": "Asphalt",
"distance_in_route": 63.907961669884
},
{
"lat": 51.282566,
"lng": 1.081581,
"elevation": 10.3,
"road_type": "Street",
"surface_type": "Asphalt",
"distance_in_route": 77.621220416651
},
{
"lat": 51.28256,
"lng": 1.081968,
"elevation": 10.37,
"road_type": "Street",
"surface_type": "Asphalt",
"distance_in_route": 104.55455468449
},
{
"lat": 51.282517,
"lng": 1.081969,
"elevation": 10.47,
"road_type": "Street",
"surface_type": "Asphalt",
"distance_in_route": 109.33806433075
},
{
"lat": 51.282277,
"lng": 1.081835,
"elevation": 11.04,
"road_type": "Street",
"surface_type": "Asphalt",
"distance_in_route": 137.61498933112
},
{
"lat": 51.282172,
"lng": 1.081775,
"elevation": 11.24,
"road_type": "Street",
"surface_type": "Asphalt",
"distance_in_route": 150.01801872967
},
{
"lat": 51.28193,
"lng": 1.081596,
"elevation": 11.6,
"road_type": "Street",
"surface_type": "Asphalt",
"distance_in_route": 179.67764201062
},
{
"lat": 51.281765,
"lng": 1.081512,
"elevation": 12.01,
"road_type": "Street",
"surface_type": "Asphalt",
"distance_in_route": 198.93906771362
},
],
"pois": []
}
````

**No results**
{
"error": "No route data"
}
