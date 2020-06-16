# Private Endpoints - Trade Cancel Orders

## POST - Cancel an order

```shell
curl --location --request POST 'https://api.sparrowsandbox.com/trades/book/cancel/c7f68417-839c-4c60-abdf-162e66327e48' \
--header 'Authorization: Your Authorization Token' \
--header 'api-key: Your API Key ID' \
--data-raw ''
```


### URL Endpoint
`https://api.sparrowsandbox.com/trades/book/cancel/:trade`

### HEADERS
Parameter |  value
--------- | ------- 
Authorization | Your authorization key
api-key | Your API Key ID

### PARAMS
Parameter |  value
--------- | ------- 
trade | c7f68417-839c-4c60-abdf-162e66327e48

<!-- ----- -->

## POST - Bulk Cancel Order

```shell
curl --location --request POST 'https://api.sparrowsandbox.com/trades/book/bulkCancel' \
--header 'Content-Type: application/json' \
--header 'Authorization: Your Authorization Token' \
--header 'api-key: Your API Key ID' \
--data-raw '{
	"tradeIds": [
		"80bc25a6-25a3-4424-9c1f-d46cbc88998f",
		"c74498aa-69ab-42f3-b3ef-1e930cdc7167"
	]
}'
```

> Example Body

```json
{
	"tradeIds": [
		"80bc25a6-25a3-4424-9c1f-d46cbc88998f",
		"c74498aa-69ab-42f3-b3ef-1e930cdc7167"
	]
}
```


### URL Endpoint
`https://api.sparrowsandbox.com/trades/book/bulkCancel`

### HEADERS
Parameter |  value
--------- | ------- 
Authorization | Your authorization key
api-key | Your API Key ID

