# Profile

A profile has the following properties:

 - name: The name of person or company
 - guid: a unique id for the profile
 - companies: a list of companies that a profile is a member of
 - id: sequential id
 - user: user account of the profile (not required, integer)
 - active_since: creation date of account
 - deactivated_since: date that the profile was removed from the system
 - is_company: flag for whether profile is a company or not
 - email: email address for the profile
 - admins: list of users who can pay invoices and withdraw money

## Create a profile
 
`POST https://beta.choosefluid.com/v1/profiles`
 
Example request
 
```shell
curl -v -u 1971800d4d82861d8f2c1651fea4d212:api_token \
	-H "Content-Type: application/json" \
	-X POST https://beta.choosefluid.com/v1/profiles
``` 

```json
[{
    "name": "Julian Threatt Test 2", 
    "companies": [
        {
            "id": 1, 
            "name": "Julian Threatt Test 2"
        }, 
        {
            "id": 19, 
            "name": "The Hat Rack"
        }
    ], 
    "id": 1, 
    "guid": "c49a63619e8d4d6dbfd6467a5bead146", 
    "user": 1, 
    "active_since": "2014-09-30", 
    "deactivated_since": null, 
    "is_company": false, 
    "email": "porfirio84@gmail.com", 
    "admins": [
        1, 
        19, 
        21, 
        29
    ]
}]
```

## Get profile details

`GET https://beta.choosefluid.com/v1/profiles/{profile_id}`

Example request

```shell
curl -v -u 1971800d4d82861d8f2c1651fea4d212:api_token \
	-H "Content-Type: application/json" \
	-X GET https://beta.choosefluid.com/v1/profiles/1
```

Successful response

```json
{
    "name": "Julian Threatt Test 2", 
    "companies": [
        {
            "id": 1, 
            "name": "Julian Threatt Test 2"
        }, 
        {
            "id": 19, 
            "name": "The Hat Rack"
        }
    ], 
    "id": 1, 
    "guid": "c49a63619e8d4d6dbfd6467a5bead146", 
    "user": 1, 
    "active_since": "2014-09-30", 
    "deactivated_since": null, 
    "is_company": false, 
    "email": "porfirio84@gmail.com", 
    "admins": [
        1, 
        19, 
        21, 
        29
    ]
}
```

## Update a profile

[need a put example as well]

`PATCH https://beta.choosefluid.com/v1/profiles/{profile_id}`

[anyhting to take note of]

Example request

```shell
curl -v -u 1971800d4d82861d8f2c1651fea4d212:api_token \
	-H "Content-Type: application/json" \
	-d '{"name": "Julian Threatt Test"} \
	-X PATCH https://beta.choosefluid.com/v1/profiles/1
```

Successful response
```json
{
    "name": "Julian Threatt Test", 
    "companies": [
        {
            "id": 1, 
            "name": "Julian Threatt Test"
        }, 
        {
            "id": 19, 
            "name": "The Hat Rack"
        }
    ], 
    "id": 1, 
    "guid": "c49a63619e8d4d6dbfd6467a5bead146", 
    "user": 1, 
    "active_since": "2014-09-30", 
    "deactivated_since": null, 
    "is_company": false, 
    "email": "porfirio84@gmail.com", 
    "admins": [
        1, 
        19, 
        21, 
        29
    ]
}
```

## Delete a client
`DELETE https://beta.choosefluid.com/v1/profile/{profile_id}`

Example request

```shell
curl -v -u 1971800d4d82861d8f2c1651fea4d212:api_token \
	-X DELETE https://beta.choosefluid.com/v1/profiles/1
```

Successful request will return `200 OK`. If the user has no acces to delete, you'll get a status code `4xx`.