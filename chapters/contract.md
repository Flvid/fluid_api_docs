# Contract

Contract has the following properties:

- editable: whether a contract is editable
- admin: profiles that are allowed to approve invoices
- id: sequential id
- guid: unique id
- name: contracts name
- create: creation date
- submitted: date the contract has be activated
- expires: date the contract has been deactivated (can be in the future)
- type: type of contract
- quantity: number of delivarable
- rate: rate of deal
- description: description of contract
- notes: notes about contract
- term: sub terms of contract
- owner: company or person who pays invoices
- team: profiles who can submit invoices against this contract
- attachments: list of attachments

## Create a contract

`POST https://beta.choosefluid.com/v1/contracts`

Example request

```shell
curl -v -u 1971800d4d82861d8f2c1651fea4d212:api_token \
	-h "Contrent-Type: application/json" \
	-X POST https://beta.choosefluid.com/v1/contracts
```

Successful response
```json
[{
    "editable": true, 
    "admin": [], 
    "id": 91, 
    "guid": "9f59a480ad50496099eb10470d6b94e3", 
    "name": "Test Contract", 
    "created": "2015-04-21", 
    "submitted": null, 
    "expires": null, 
    "type": "h", 
    "quantity": 1, 
    "rate": "1", 
    "description": "", 
    "notes": "", 
    "term": null, 
    "owner": 1, 
    "team": [], 
    "attachments": []
}]
```

## Get contract details

`GET https://beta.choosefluid.com/v1/contracts/{contract_id}`

Example request

```shell
curl -v -u 1971800d4d82861d8f2c1651fea4d212:api_token \
	-X GET https://beta.choosefluid.com/contracts/91
```

Successful response

```json
{
"editable": true, 
"admin": [], 
"id": 91, 
"guid": "9f59a480ad50496099eb10470d6b94e3", 
"name": "Test Contract", 
"created": "2015-04-21", 
"submitted": null, 
"expires": null, 
"type": "h", 
"quantity": 1, 
"rate": "1", 
"description": "", 
"notes": "", 
"term": null, 
"owner": 1, 
"team": [], 
"attachments": []
}
```

## Update a contract

`PATCH https://beta.choosefluid.com/v1/contracts/{contract_id}`

Example Request

```shell
curl -v -u 1971800d4d82861d8f2c1651fea4d212:api_token \
	-H "Content-Type: application/json" \
	-d "{"name": "Different name"}"
	-X PATCH https://beta.choosefluid.com/v1/contracts/91
```

Successful response

```json
{
"editable": true, 
"admin": [], 
"id": 91, 
"guid": "9f59a480ad50496099eb10470d6b94e3", 
"name": "Test Contract", 
"created": "2015-04-21", 
"submitted": null, 
"expires": null, 
"type": "h", 
"quantity": 1, 
"rate": "1", 
"description": "", 
"notes": "", 
"term": null, 
"owner": 1, 
"team": [], 
"attachments": []
}
```

