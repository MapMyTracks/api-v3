Map My Tracks API (v3)
===
The Map My Tracks API provides a simple interface that allows developers to access user accounts and update activity data. You can use this API to make your own applications seamlessly integrate with Map My Tracks.

The Map My Tracks API (v3) is currently available for approved developers only. If you are a developer of a fitness application or fitness device and would like access to the Map My Tracks API please get in touch at support@mapmytracks.com with details of your project.

Authorization
---

The Map My Tracks API (v3) supports the OAuth 2 specification.

Applications acquire an OAuth access token for a user by following these steps: -

1. Register your application with us by emailing details of your project to [support@mapmytracks.com](mailto:support@mapmytracks.com). Once approved, we will supply you with a `client_id` and `client_secret`.
2. Redirect the user to `https://www.mapmytracks.com/api3/oauth/authorize` passing your `client_id`, a `redirect_url` and `reponse_type=code`
3. Upon authorization, the user will be redirected to your `redirect_url` with a `code` parameter appended to the URI.
4. Exchange this code for an access and refresh tokens by calling `http://www.mapmytracks.com/api3/oauth/token` with `grant_type=authorization_code`, your original `redirect_url` and your `code`. Requests should be authenticated with a Basic HTTP Authentication header containing your `client_id` and `client_secret`.

```
# Example cURL to obtain an access token with an authorization code
curl -u <client_id>:<client_secret> https://www.mapmytracks.com/api3/oauth/token -d 'grant_type=authorization_code&redirect_uri=<redirect_url>&code=<code>'
```

5. When the access token expires, call `https://www.mapmytracks.com/api3/oauth/token` with `grant_type=refresh_token` and your `refresh_token` to obtain a new access token. Please note, as well as issuing a new access token, the system also issues a new refresh token that should be used on the next call. The refresh token that was supplied is expired and cannot be used again.

```
# Example cURL to obtain an access token with a refresh token
curl -u <client_id>:<client_secret> https://www.mapmytracks.com/api3/oauth/token -d 'grant_type=refresh_token&refresh_token=<refresh_token>'
```

Applications can de-authorize tokens by calling `http://www.mapmytracks.com/api3/oauth/revoke` and passing the `code` that is to be revoked. To revoke a refresh token, also pass `token_type_hint=refresh_token`.

```
# Example cURLs to revoke access and refresh tokens
curl --data "token=<access_token>" https://www.mapmytracks.com/api3/oauth/revoke
curl --data "token=<refresh_token>&token_type_hint=refresh_token" https://www.mapmytracks.com/api3/oauth/revoke
```

---

Overview
---
All requests should be authenticated with an OAuth2 access token. All API requests will be assigned to the authenticated user's Map My Tracks account. All requests should be made over HTTPS and all API reponses are JSON encoded.

**Data input**
* [Upload activity](endpoints/upload_activity.md)
* [start activity](endpoints/start_activity.md)
* [update activity](endpoints/update_activity.md)
* [stop activity](endpoints/stop_activity.md)

