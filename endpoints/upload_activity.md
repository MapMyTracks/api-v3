Upload activity
====
Upload an activity to Map My Tracks. Activities can be formatted as either `GPX`, `FIT` or `TCX` files.

Parameters
---

- `status` *(required)*

Indicates if this activity is to be public visible on Map My Tracks, or private and only visible to the user making the API call. Possible values are "public" and "private".

- `activity` *(required if file format is not `FIT`)*

The activity type. Possible values are "canoeing", "cross country skiing", "cycling", "driving", "enduro", "flying", "gliding", "hand cycling", "hang gliding", "hiking", "horse riding", "hot air ballooning", "kayaking", "kiteboarding", "miscellaneous", "motor racing", "motorcycling", "mountain biking", "mountaineering", "nordic walking", "off road driving", "orienteering", "paragliding", "rowing", "running", "sailing", "sea kayaking","snowshoeing","jet skiing","powerboating","indoor cycling", "skateboarding", "skating", "skiing", "snowboarding", "stand up paddle boarding", "swimming", "walking", "wheelchair", "windsurfing".

- `file` *(required)*

A `GPX`, `FIT` or `TCX` file containing the activity.

- `activity_name`

The activity name that will appear on Map My Tracks.

Response
---

If the upload was successful, the API returns a JSON formatted reply indicating the unique identifier for the activity on Map My Tracks. A status propery indicates if the activity was newly created or found to already exist. Successful request have a HTTP response code of 200.
In the event the upload was not successful, the API returns a JSON formatted reply that indicates the reason for the failure. These error messages have a HTTP response code of 403.


Example
---

```
curl -H 'Authorization: Bearer <access_token>' -F 'status=<status>' -F 'activity_type=<activity_type>' -F 'file=@<filename>' https://www.mapmytracks.com/api3/uploadActivity
```

**Success:**
```
{"function":"uploadActivity","activity_id":1234567}
```

**Error:**
```
{"function":"uploadActivity","error":"INVALID_PARAMENTER","message":"invalid status"}
```
