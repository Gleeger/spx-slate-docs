# Private Endpoints - Contract

## GET - Display own trade contracts


```shell
curl --location --request GET 'https://api.sparrowsandbox.com/trades/contracts/own' \
--header 'Authorization: Your Authorization Token' \
--header 'api-key: Your API Key ID'
```


### URL Endpoint
`https://api.sparrowsandbox.com/trades/contracts/own`

### HEADERS
Parameter |  value
--------- | ------- 
Authorization | Your authorization key
api-key | Your API Key ID


<!-- END -->

## GET - Display own active trade contracts


```shell
curl --location --request GET 'https://api.sparrowsandbox.com/trades/contracts/own?status=active' \
--header 'Authorization: Your Authorization Token' \
--header 'api-key: Your API Key ID'
```


### URL Endpoint
`https://api.sparrowsandbox.com/trades/contracts/own?status=active`

### HEADERS
Parameter |  value
--------- | ------- 
Authorization | Your authorization key
api-key | Your API Key ID

### Params
Parameter |  value
--------- | ------- 
status | active


<!-- END -->

## GET - Display own settled trade contracts


```shell
curl --location --request GET 'https://api.sparrowsandbox.com/trades/contracts/own?status=settled' \
--header 'Authorization: Your Authorization Token' \
--header 'api-key: Your API Key ID'
```


### URL Endpoint
`https://api.sparrowsandbox.com/trades/contracts/own?status=settled`

### HEADERS
Parameter |  value
--------- | ------- 
Authorization | Your authorization key
api-key | Your API Key ID

### Params
Parameter |  value
--------- | ------- 
status | settled


<!-- END -->

## GET - Display own buy trade contracts


```shell
curl --location --request GET 'https://api.sparrowsandbox.com/trades/contracts/own?filter=buy' \
--header 'Authorization: Your Authorization Token' \
--header 'api-key: Your API Key ID'
```

### URL Endpoint
`https://api.sparrowsandbox.com/trades/contracts/own?filter=buy`

### HEADERS
Parameter |  value
--------- | ------- 
Authorization | Your authorization key
api-key | Your API Key ID

### Params
Parameter |  value
--------- | ------- 
filter | buy


<!-- END -->

## GET - Display own sell trade contracts


```shell
curl --location --request GET 'https://api.sparrowsandbox.com/trades/contracts/own?filter=sell' \
--header 'Authorization: Your Authorization Token' \
--header 'api-key: Your API Key ID'
```

### URL Endpoint
`https://api.sparrowsandbox.com/trades/contracts/own?filter=sell`

### HEADERS
Parameter |  value
--------- | ------- 
Authorization | Your authorization key
api-key | Your API Key ID

### Params
Parameter |  value
--------- | ------- 
filter | sell


<!-- END -->

## GET - Display own trade contracts - custom


```shell
curl --location --request GET 'https://api.sparrowsandbox.com/trades/contracts/own?filter=sell&status=settled' \
--header 'Authorization: Your Authorization Token' \
--header 'api-key: Your API Key ID'
```

### URL Endpoint
`https://api.sparrowsandbox.com/trades/contracts/own?filter=sell&status=settled`

### HEADERS
Parameter |  value
--------- | ------- 
Authorization | Your authorization key
api-key | Your API Key ID

### Params
Parameter |  value
--------- | ------- 
filter | sell
status | settled


<!-- END -->

## GET - Display own trade contracts (group by market)


```shell
curl --location --request GET 'https://api.sparrowsandbox.com/trades/contracts/own?format=grouped' \
--header 'Authorization: Your Authorization Token' \
--header 'api-key: Your API Key ID'
```

### URL Endpoint
`https://api.sparrowsandbox.com/trades/contracts/own?format=grouped`

### HEADERS
Parameter |  value
--------- | ------- 
Authorization | Your authorization key
api-key | Your API Key ID

### Params
Parameter |  value
--------- | ------- 
format | grouped (list / grouped (default is list) refer to TRD-CN-1a)


<!-- END -->

## GET - Display all trade contracts


```shell
curl --location --request GET 'https://api.sparrowsandbox.com/trades/contracts' \
--header 'Authorization: Your Authorization Token' \
--header 'api-key: Your API Key ID'
```

By default, sorted by createdAt and status is ACTIVE


### URL Endpoint
`https://api.sparrowsandbox.com/trades/contracts`

### HEADERS
Parameter |  value
--------- | ------- 
Authorization | Your authorization key
api-key | Your API Key ID


<!-- END -->

## GET - Display all settled trade contracts


```shell
curl --location --request GET 'https://api.sparrowsandbox.com/trades/contracts?status=settled' \
--header 'Authorization: Your Authorization Token' \
--header 'api-key: Your API Key ID'
```

### URL Endpoint
`https://api.sparrowsandbox.com/trades/contracts?status=settled`

### HEADERS
Parameter |  value
--------- | ------- 
Authorization | Your authorization key
api-key | Your API Key ID

### PARAMS
Parameter |  value
--------- | ------- 
status | settled


<!-- END -->

## GET - Display all put trade contracts


```shell
curl --location --request GET 'https://api.sparrowsandbox.com/trades/contracts?type=put' \
--header 'Authorization: Your Authorization Token' \
--header 'api-key: Your API Key ID'
```

### URL Endpoint
`https://api.sparrowsandbox.com/trades/contracts?type=put`

### HEADERS
Parameter |  value
--------- | ------- 
Authorization | Your authorization key
api-key | Your API Key ID

### PARAMS
Parameter |  value
--------- | ------- 
type | put


<!-- END -->

## GET - Display all call trade contracts


```shell
curl --location --request GET 'https://api.sparrowsandbox.com/trades/contracts?type=call' \
--header 'Authorization: Your Authorization Token' \
--header 'api-key: Your API Key ID'
```

### URL Endpoint
`https://api.sparrowsandbox.com/trades/contracts?type=put`

### HEADERS
Parameter |  value
--------- | ------- 
Authorization | Your authorization key
api-key | Your API Key ID

### PARAMS
Parameter |  value
--------- | ------- 
type | put


<!-- END -->