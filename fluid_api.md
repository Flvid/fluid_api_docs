# Fluid API v1 [WIP]
----
The api accepts json and xml requests. Please make sure you're setting `Content-Type: application/json`or `Content-Type: application/json` in your request header. Each request returns a **JSON-encoded** or **XML-encoded** body. The result of each action is communicated via standard HTTP Response codes.

## CORS
If you wish to use the API using CORS, we'l need to whitelist you first. Please send us a note at support@choosefluid.com to whitelist your domain(s).

## Successful requests
When the request is successful (2XX), a nested response object is returned. 

Example request

```shell
curl -v -u 1971800d4d82861d8f2c1651fea4d212:api_token \
	-H "Content-Type: application/json" \
	-d '{"time_entry":{"description":"New time entry","created_with":"API example code","start":"2012-02-12T15:35:47+02:00","duration":1200,"wid":31366}}' \
	 -X POST https://www.toggl.com/api/v8/time_entries

```

Response

```json
{
    "data": {
        "description": "New time entry",
        "start": "2013-02-12T15:35:47+02:00",
        "billable": false,
        "wid": 31366,
        "pid": 9012,
        "duration": 1200,
        "stop": "2013-02-12T15:35:57+02:00",
        "tags": [
         	"billed"
        ],
        "id": 4269795
    }
}
```

## Failed Requests

If a create or update action failed, HTTP status code 404 and an array of localized error messages will be returned.

```shell
curl -v -u 1971800d4d82861d8f2c1651fea4d212:api_token \
	-H 'Content-Type: application/json' \
	-d '{"time_entry":{"description":"New time entry","created_with":"API example code"}}' \
	-X POST https://www.toggl.com/api/v8/time_entries
```

Response

`["Start can't be blank"]`

## Authentication

To use the API, you need to authenticate yourself. This can be done via HTTP POST. After successful authentication a session is created using a cookie.

if authentication fails, HTTP status code 403 is returned. You can read more about authentication and see sample requests [here](chapters/authentication.md)

## Supported API requests

* [Authenticate and get user data](chapters/authentication.md)
 - HTTP Basic Auth with API token
 - Authentication with a session cookie
 - Destroy the session
* [Profile](chapters/profile.md)
 - create a profile
 - get a profile's details
 - update a profile
 - delete a profile
 - get profiles visible to a user
 - get profile projects
* [Contract](chapters/contract.md)
 - create a contract
 - get a contract's details
 - update a contract
 - delete a contract
 - get a contracts admins
 - get a contracts recipients
* [Invoice](chapters/invoice.md)
 - create a invoice
 - get a invoice's details
 - update an invoice
 - delete an invoice
 - get an invoice's admins
* [Attachment](chapters/attachment.md)
 - create an attachment
 - download an attachment
 - download an attachment