Stop an activity - Beta
====
Stop an activity on Map My Tracks. 

Parameters
---

- `activity_id`  *(required)*

The activity ID

Response
---

If the request was successful, the API returns a JSON formatted reply indicating if the activity was successfully stopped on Map My Tracks. A status propery indicates if the activity was stopped. Successful requests have a HTTP response code of 200. In the event the activity was not successful, the API returns a JSON formatted reply that indicates the reason for the failure. These error messages have a HTTP response code of 403.


Example
---

```
curl -H 'Authorization: Bearer <access_token>' -F 'activity_id=123456' http://www.mapmytracks.com/api3/stopActivity
```

**Success:**
```
{"function":"stopActivity","ok":1}
```

**Error:**
```
{"function":"stopActivity","error":<errorCode>}
```
