Update an activity - Beta
====
Update an activity on Map My Tracks. 

Parameters
---


- `activity_id`

The activity id for which track to update on Map My Tracks



- `data` *(required)*

Below outlines the data to include within the request. Some are a requirement, others are not Provide this data as a JSON object. 

    - `loc`  *(required)*

    The location data, required in JSON format, for example:

    ```
    {"loc" : [{"lat" : 1.1111, "lon" : 51.1122, "timestamp" : 1563809643, "unix_timestamp" : 1563809643, "ele" : 0.1}]}
    ```

    - `hr`  *(required)*

    Heart rate data

    ```
    {"loc" : [{"hr" : 50, "timestamp" : 1563809643, "unix_timestamp" : 1563809643}]}
    ```




Response
---

If the request was successful, the API returns a JSON formatted reply indicating the unique identifier for the activity on Map My Tracks. A status propery indicates if the activity was updated. Successful requests have a HTTP response code of 200.
In the event the activity was not successful, the API returns a JSON formatted reply that indicates the reason for the failure. These error messages have a HTTP response code of 403.


Example
---

```
curl -H 'Authorization: Bearer <access_token>' -F 'status=private' -F 'activity_type=Running' -F'data={"loc" : [{"lat" : 1, "lon" : 1, "timestamp" : 1.1, "unix_timestamp" : 1000}]}' http://www.mapmytracks.com/api3/updateActivity
```

**Success:**
```
{"function":"updateActivity","ok":1}
```

**Error:**
```
{"function":"updateActivity","error":"INVALID_PARAMENTER","message":"invalid parameters"}
```
