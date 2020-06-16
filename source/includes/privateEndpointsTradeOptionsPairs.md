# Private Endpoints - Trade Options Pairs

## GET - Display Options Trading Pairs
```shell
curl --location --request GET 'https://api.sparrowsandbox.com/trades/pairs' \
--header 'Authorization: Your Authorization Token' \
--header 'api-key: Your API Key ID'
```

> Example Response

```json
[
  {
    "pair": "ETH-SP$",
    "strikeStep": "10",
    "amountStep": "1",
    "unitPremiumStep": "0.01"
  },
  {
    "pair": "BTC-SP$",
    "strikeStep": "250",
    "amountStep": "0.1",
    "unitPremiumStep": "0.01"
  }
]
```

### URL Endpoint
`https://api.sparrowsandbox.com/trades/pairs`

### HEADERS
Parameter | Default 
--------- | ------- 
Authorization | Your Authorization Token
api-key | Your API KEY ID

<!-- END  GET - (Option Pairs) Display Options Trading Pairs -->

