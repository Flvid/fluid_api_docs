# Authentication

To use the API, you need to authenticate yourself. This can be done via OAuth2 authentication.

## OAuth 2

OAuth 2 is an authorization framework that enables applications to obtain limited access to user accounts on a HTTP service. It works by delegating user authentication to the service that hosts the user account, and authorizing third-party applications to access the user account. OAuth 2 provides authorization flows for web, desktop, and mobile devices

We currently only support the authorization code authorization grant type (server side support). If you are interested in other authorization grant types, please contact our support team, support@choosefluid.com

### Initiate authentication process

OAuth2 is always initiated by the user. You will need to provide your users with an authorization link, so that they can initiate the authorization process. When your user clicks the link they will be redirected to our authorization server, where they will be prompted to enter their username and password. If they don't have an account with us, they will be asked to create an account. Once they have signed in they can authorize your access to their account.

Example link

`https://beta.choosefluid.com/v1/auth/authorize/?response_type=code&client_id=[client_id]&state=random_state_string&redirect_uri=[redirect_uri]`

Once the user has given their authorization, our authentication server will redirect to your designated redirect url. The authorization code will be and state variable will be attached as GET data.

Example Redirect link

`https://example.com/?state=random_state_string&code=[authorization_code]`

### Request an access token

`POST https://beta.choosefluid.com/v1/auth/token/`

You should take the authorization code and use it to request an access token. Request the access token immediately, since they authorization codes do expire. If the authorization code expires you will receive a 401 response {"error": "invalid_grant"}

Example request

```shell
curl -v -d "code=[authorization_code]&grant_type=authorization_code" \
-u "[client_id]:[client_secret]" \
-X POST https://beta.choosefluid.com/v1/auth/token/
```

Example Response

```json
{
	"access_token": "[access_token]",
	"token_type": "Bearer",
	"expires_in": 36000,
	"refresh_token": "[refresh_token]",
	"scope": "read write"
}
```

### Use the access token

Now that you have an access token you can use the access token to access api endpoints.

Example request

```shell
curl -H "Authorization: Bearer [access_token]" -X GET https://beta.choosefluid.com/v1/[object]
```

### Refresh token

Eventually the access token will expire and you will need to refresh it in order to continue using the token.

Example request

```shell
curl -v -d "refresh_token=[refresh_token]&grant_type=refresh_token" \
-u "[client_id]:[client_secret]" \
-X POST https://beta.choosefluid.com/v1/auth/token/
```

Example response

```json
{
	"access_token": "[new_access_token]",
	"token_type": "Bearer",
	"expires_in": 36000,
	"refresh_token": "[new_refresh_token]",
	"scope": "read write"
}
```

If you have any questions please contact support@choosefluid.com
