# Invoices

Invoice has the following properties

 - state: state of the invoice draft, approved, etc.
 - name: name of the invoice
 - id: sequential id
 - guid: universal id
 - type: type of invoice (inherited from the contract)
 - contract: the contract the invoice is for
 - created: the date the invoice was created
 - submitted: the date the invoice was submitted
 - date_accepted: the date the invoice was approved
 - quantity: the amount of the deliverable
 - rate: the rate
 - profile: the profile submitting the invoice
 - notes: notes
 - paid: the date the profile was paid
 - closed: the date the owner of the contract paid fluid
 - attachments: attachments

## Create a invoice

`POST https://beta.choosefluid.com/v1/invoices`

Example request

```shell
curl -v -u 1971800d4d82861d8f2c1651fea4d212:api_token \
	-h "Contrent-Type: application/json" \
	-X POST https://beta.choosefluid.com/v1/invoices
```

Successful response
```json
[{
    "editable": true, 
    "state": null, 
    "name": "New Invoice", 
    "id": 22, 
    "guid": "abde0470b48c45b58147e1a65d370dc3", 
    "type": "d", 
    "contract": 90, 
    "created": "04/21/15 at 07:16 PM", 
    "submitted": null, 
    "date_accepted": null, 
    "quantity": 1, 
    "rate": "1", 
    "profile": 1, 
    "notes": "", 
    "paid": null, 
    "closed": null, 
    "attachments": []
}]
```

## Get invoice details

`GET https://beta.choosefluid.com/v1/invoices/{invoice_id}`

Example request

```shell
curl -v -u 1971800d4d82861d8f2c1651fea4d212:api_token \
	-X GET https://beta.choosefluid.com/invoices/91
```

Successful response

```json
{
"editable": true, 
"state": null, 
"name": "New Invoice", 
"id": 22, 
"guid": "abde0470b48c45b58147e1a65d370dc3", 
"type": "d", 
"contract": 90, 
"created": "04/21/15 at 07:16 PM", 
"submitted": null, 
"date_accepted": null, 
"quantity": 1, 
"rate": "1", 
"profile": 1, 
"notes": "", 
"paid": null, 
"closed": null, 
"attachments": []
}
```

## Update a invoice

`PATCH https://beta.choosefluid.com/v1/invoices/{invoice_id}`

Example Request

```shell
curl -v -u 1971800d4d82861d8f2c1651fea4d212:api_token \
	-H "Content-Type: application/json" \
	-d "{"name": "Different name"}"
	-X PATCH https://beta.choosefluid.com/v1/invoices/91
```

Successful response

```json
{
"editable": true, 
"state": null, 
"name": "Different name", 
"id": 22, 
"guid": "abde0470b48c45b58147e1a65d370dc3", 
"type": "d", 
"contract": 90, 
"created": "04/21/15 at 07:16 PM", 
"submitted": null, 
"date_accepted": null, 
"quantity": 1, 
"rate": "1", 
"profile": 1, 
"notes": "", 
"paid": null, 
"closed": null, 
"attachments": []
}
```

