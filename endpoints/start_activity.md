Start activity (beta)
====
Start an activity on Map My Tracks. 

Parameters
---

- `status` *(required)*

Indicates if this activity is to be public visible on Map My Tracks, or private and only visible to the user making the API call. Possible values are "public" and "private".

- `activity_type` 

The activity type. Possible values are "canoeing", "cross country skiing", "cycling", "driving", "enduro", "flying", "gliding", "hand cycling", "hang gliding", "hiking", "horse riding", "hot air ballooning", "indoor cycling", "inline skating", "jet skiing", "kayaking", "kiteboarding", "miscellaneous", "motor racing", "motorcycling", "mountain biking", "mountaineering", "nordic walking", "off road driving", "orienteering", "paragliding", "powerboating", "rowing", "running", "sailing", "sea kayaking","snowshoeing","jet skiing","powerboating","indoor cycling", "skateboarding", "skating", "skiing", "snowboarding", "stand up paddle boarding", "swimming", "walking", "wheelchair", "windsurfing".

- `activity_title`

The activity title that will appear on Map My Tracks. If an activity already exists with the same name under the member the track will be updated.

- `tags`

Tags the activity with certain associations for use on Map My Tracks, for example "canterbury"



- `Activity Data` *(required)*

Below outlines the data to include within the request. Some are a requirement, others are not. 

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

If the activity was successful, the API returns a JSON formatted reply indicating the unique identifier for the activity on Map My Tracks. A status propery indicates if the activity was newly created or found to already exist. Successful requests have a HTTP response code of 200.

In the event the activity was not successful, the API returns a JSON formatted reply that indicates the reason for the failure. These error messages have a HTTP response code of 403.


Example
---

```
curl -H 'Authorization: Bearer <access_token>' -F 'status=private' -F 'activity_type=Running' -F'data={"loc" : [{"lat" : 1, "lon" : 1, "timestamp" : 1.1, "unix_timestamp" : 1000}]}' https://www.mapmytracks.com/api3/startActivity
```

**Success:**
```
{"function":"startActivity","activity_id":1234567}
```

**Error:**
```
{"function":"startActivity","error":"INVALID_PARAMENTER","message":"invalid parameters"}
```
