# FoxBase
FoxBase is an online **database** that you can use to store your data.

## Supported types of data
**FoxBase** supports both associative and list data schemas.

## Endpoint
FoxBase is hosted on the UCS and you can access to the `v1` via the following endpoint:
```
https://api.ucserver.it/foxbase/v1
```

## Create a database
```
POST /database

Body:
{
  "type": string, [associative or list]
  "sameip": bool, if the database can be accessed by the IP that created it
}
```
Response (json):
```
HTTP 201 Created
```
```json
{
	"status": 201,
	"message": "Created",
	"id": "BY3jIDERFioQeDdFDEvc[...]c58cc2b8",
	"remaining": 14
}
```
You will have to use the given `id` to access the database

## Associative databases
### Get every database entry
```
GET /database/<database id>
```
Response (json):
```
HTTP 200 OK
```
```json
[]
```

### Get a specific item from the index
```
GET /database/<database id>/<index>/index
```
Response (json):
```
HTTP 200 OK
```
```
uwu
```

### Get the index of a specific item
If more items with the same entry exists the first one will be returned!
> [!WARNING]
> That feature is not available at the moment!

### Add a new entry to the database
```
POST /database/<database id>
Body:
whatever you want to add
```
Response (json):
```
HTTP 201 Created
```

### Edit an element at the given index
