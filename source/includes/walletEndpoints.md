# Wallet

## Wallet Balance
```shell
curl --location --request GET 'https://api.sparrowexchange.com/wallets/balance' \
--header 'Authorization: Your Authorization Token' \
--header 'api-key: Your API Key ID' \
--header 'Content-Type: application/json'
```

> Example Response

```json
[
  {
    "coin": "BTC",
    "coinName": "Bitcoin",
    "available": "2.35415896",
    "on_trade": "0",
    "total": "2.35415896",
    "withdrawable": true,
    "depositable": true,
    "market": "CRYPTO"
  },
  {
    "coin": "SP$",
    "coinName": "Sparrow Dollar",
    "available": "1.99",
    "on_trade": "0",
    "total": "1.999",
    "withdrawable": false,
    "depositable": false,
    "market": "CASH"
  },
  {
    "coin": "SPO",
    "coinName": "Sparrow Token",
    "available": "666.038320158102766833",
    "on_trade": "0",
    "total": "666.038320158102766833",
    "withdrawable": true,
    "depositable": true,
    "market": "CRYPTO"
  },
  {
    "coin": "ETH",
    "coinName": "Ethereum",
    "available": "0",
    "on_trade": "0",
    "total": "0",
    "withdrawable": true,
    "depositable": true,
    "market": "CRYPTO"
  },
  {
    "coin": "USDT",
    "coinName": "Tether",
    "available": "0",
    "on_trade": "0",
    "total": "0",
    "withdrawable": true,
    "depositable": true,
    "market": "CRYPTO"
  },
  {
    "coin": "PAX",
    "coinName": "Paxos Standard",
    "available": "0",
    "on_trade": "0",
    "total": "0",
    "withdrawable": true,
    "depositable": true,
    "market": "CRYPTO"
  },
  {
    "coin": "TUSD",
    "coinName": "TrueUSD",
    "available": "0",
    "on_trade": "0",
    "total": "0",
    "withdrawable": true,
    "depositable": true,
    "market": "CRYPTO"
  },
  {
    "coin": "USDC",
    "coinName": "USD Coin",
    "available": "0",
    "on_trade": "0",
    "total": "0",
    "withdrawable": true,
    "depositable": true,
    "market": "CRYPTO"
  },
  {
    "coin": "XRP",
    "coinName": "Ripple",
    "available": "0",
    "on_trade": "0",
    "total": "0",
    "withdrawable": true,
    "depositable": true,
    "market": "CRYPTO"
  },
  {
    "coin": "XLM",
    "coinName": "Stellar",
    "available": "0",
    "on_trade": "0",
    "total": "0",
    "withdrawable": true,
    "depositable": true,
    "market": "CRYPTO"
  }
]
```

### URL Endpoint
`GET https://api.sparrowexchange.com/wallets/balance`

### HEADERS
Parameter | Default 
--------- | ------- 
Authorization | Your Authorization Token
api-key | Your API KEY ID
Content-Type | application/json

<!-- END GET - WALLET BALANCE -->
<!-- ------ -->

<!-- START GET - WALLET BALANCE (ONLY OPTIONS TRADING PAIRS) -->
## Wallet Balance (Options Trading Pairs Only)

```shell
curl --location --request GET 'https://api.sparrowexchange.com/wallets/balance?filter=optionsTrading' \
--header 'Authorization: Your Authorization Token' \
--header 'api-key: Your API Key ID'
```

> Example Response

```json
[
  {
    "coin": "BTC",
    "coinName": "Bitcoin",
    "available": "2.35415896",
    "on_trade": "0",
    "total": "2.35415896",
    "withdrawable": true,
    "depositable": true,
    "market": "CRYPTO"
  },
  {
    "coin": "SP$",
    "coinName": "Sparrow Dollar",
    "available": "1.99",
    "on_trade": "0",
    "total": "1.99",
    "withdrawable": false,
    "depositable": false,
    "market": "CASH"
  },
  {
    "coin": "SPO",
    "coinName": "Sparrow Token",
    "available": "666.038320158102766833",
    "on_trade": "0",
    "total": "666.038320158102766833",
    "withdrawable": true,
    "depositable": true,
    "market": "CRYPTO"
  },
  {
    "coin": "ETH",
    "coinName": "Ethereum",
    "available": "0",
    "on_trade": "0",
    "total": "0",
    "withdrawable": true,
    "depositable": true,
    "market": "CRYPTO"
  }
]
```

### URL Endpoint
`GET https://api.sparrowexchange.com/wallets/balance?filter=optionsTrading`

### HEADERS
Parameter | Default 
--------- | ------- 
Authorization | Your Authorization Token
api-key | Your API KEY ID
Content-Type | application/json

### PARAMS
Parameter | Default 
--------- | ------- 
filter | optionsTrading
<!-- END GET - WALLET BALANCE (ONLY OPTIONS TRADING PAIRS) -->
