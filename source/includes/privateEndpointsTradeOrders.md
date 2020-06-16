# Private Endpoints - Trade Orders

## POST - Create new trade order with unitPremium
```shell
curl --location --request POST 'https://api.sparrowsandbox.com/trades/book/create' \
--header 'Content-Type: application/json' \
--header 'Authorization: Your Authorization Token' \
--header 'api-key: Your API Key ID' \
--data-raw '{
	"action": "BUY",
	"type": "CALL",
	"lifetime": "GTD",
	"txFeeCoin": "SP$",
	"pair": "BTC-SP$",
	"strike": "8000",
	"amount": "1",
	"totalPremium": "200",
	"expiryDate": "2019-10-04T08:00"
}'
```

> Example Body

```json
{
	"action": "BUY",
	"type": "CALL",
	"lifetime": "GTD",
	"txFeeCoin": "SP$",
	"pair": "BTC-SP$",
	"strike": "8000",
	"amount": "1",
	"totalPremium": "200",
	"expiryDate": "2019-10-04T08:00:00.000Z"
}
```

> Example Response

```json
{
  "result": {
    "expiry_date": "4/10/2019",
    "iv": 1.1939,
    "option_price": 0.01,
    "quantity": 0.1,
    "spot": 7803,
    "strike": 80000
  },
  "status": "success"
}
```

### URL Endpoint
`https://api.sparrowsandbox.com/trades/book/create`

### HEADERS
Parameter | Default 
--------- | ------- 
Content-Type | application/json
Authorization | Your Authorization Token
api-key | Your API KEY ID


<!-- END  POST - Create new trade order with unitPremium -->



<!-- START POST - Create new trade order with totalPremium -->

## POST - Create new trade order with totalPremium
```shell
curl --location --request POST 'https://api.sparrowsandbox.com/trades/book/create' \
--header 'Content-Type: application/json' \
--header 'Authorization: Your Authorization Token' \
--header 'api-key: Your API Key ID' \
--data-raw '{
	"action": "BUY",
	"type": "PUT",
	"lifetime": "GTD",
	"txFeeCoin": "SP$",
	"pair": "BTC-SP$",
	"strike": "7000",
	"amount": "3",
	"totalPremium": "10",
	"expiryDate": "2019-04-20T08:00:00.000Z"
}'
```

> Example Body

```json
{
	"action": "BUY",
	"type": "PUT",
	"lifetime": "GTD",
	"txFeeCoin": "SP$",
	"pair": "BTC-SP$",
	"strike": "7000",
	"amount": "3",
	"totalPremium": "10",
	"expiryDate": "2019-10-04T08:00:00.000Z"
}
```

> Example Response

```json
{
  "result": {
    "expiry_date": "11/10/2019",
    "iv": 1.1939,
    "option_price": 0.01,
    "quantity": 0.1,
    "spot": 7803,
    "strike": 80000
  },
  "status": "success"
}
```

### URL Endpoint
`https://api.sparrowsandbox.com/trades/book/create`

### HEADERS
Parameter | Default 
--------- | ------- 
Content-Type | application/json
Authorization | Your Authorization Token
api-key | Your API KEY ID


<!-- END  POST - Create new trade order with totalPremium -->


<!-- START POST - Create new trade order with tradeUnitPremium -->
## POST - Create new trade order with tradeUnitPremium
```shell
curl --location --request POST 'https://api.sparrowsandbox.com/trades/book/create' \
--header 'Content-Type: application/json' \
--header 'Authorization: Your Authorization Token' \
--header 'api-key: Your API Key ID' \
--data-raw '{
	"action": "BUY",
	"type": "PUT",
	"lifetime": "GTD",
	"txFeeCoin": "SP$",
	"pair": "BTC-SP$",
	"strike": "7000",
	"amount": "10",
	"tradeUnitPremium": "0.2",
	"expiryDate": "2019-03-01T08:00:00.000Z"
}'
```

> Example Body

```json
{
	"action": "BUY",
	"type": "PUT",
	"lifetime": "GTD",
	"txFeeCoin": "SP$",
	"pair": "BTC-SP$",
	"strike": "7000",
	"amount": "10",
	"tradeUnitPremium": "0.2",
	"expiryDate": "2019-10-04T08:00:00.000Z"
}
```

> Example Response

```json
{
  "result": {
    "expiry_date": "11/10/2019",
    "iv": 1.1939,
    "option_price": 0.01,
    "quantity": 0.1,
    "spot": 7803,
    "strike": 80000
  },
  "status": "success"
}
```

### URL Endpoint
`https://api.sparrowsandbox.com/trades/book/create`

### HEADERS
Parameter | Default 
--------- | ------- 
Content-Type | application/json
Authorization | Your Authorization Token
api-key | Your API KEY ID


<!-- END POST - Create new trade order with tradeUnitPremium -->

<!-- START POST - Create new trade order without matching process -->
## POST - Create new trade order without matching process
```shell
curl --location --request POST 'https://api.sparrowsandbox.com/trades/book/create' \
--header 'Content-Type: application/json' \
--header 'Authorization: Your Authorization Token' \
--header 'api-key: Your API Key ID' \
--data-raw '{
	"action": "BUY",
	"type": "PUT",
	"lifetime": "GTD",
	"txFeeCoin": "SP$",
	"pair": "BTC-SP$",
	"strike": "7000",
	"amount": "0.8",
	"unitPremium": "1",
	"expiryDate": "2019-03-10T08:00:00.000Z",
	"skipBidding": true
}'
```

> Example Body

```json
{
	"action": "BUY",
	"type": "PUT",
	"lifetime": "GTD",
	"txFeeCoin": "SP$",
	"pair": "BTC-SP$",
	"strike": "7000",
	"amount": "0.8",
	"unitPremium": "1",
	"expiryDate": "2019-10-04T08:00:00.000Z",
	"skipBidding": true
}
```

> Example Response

```json
{
  "result": {
    "expiry_date": "11/10/2019",
    "iv": 1.1939,
    "option_price": 0.01,
    "quantity": 0.1,
    "spot": 7803,
    "strike": 80000
  },
  "status": "success"
}
```

### URL Endpoint
`https://api.sparrowsandbox.com/trades/book/create`

### HEADERS
Parameter | Default 
--------- | ------- 
Content-Type | application/json
Authorization | Your Authorization Token
api-key | Your API KEY ID


<!-- END POST - Create new trade order without matching process -->

<!-- START POST - Bulk Create new trade orders with unitPremium -->
## POST - Bulk Create new trade order with unitPremium
```shell
curl --location --request POST 'https://api.sparrowsandbox.com/trades/book/bulkCreate' \
--header 'Content-Type: application/json' \
--header 'Authorization: Your Authorization Token' \
--header 'api-key: Your API Key ID' \
--data-raw '[
	{
		"action": "BUY",
		"type": "PUT",
		"lifetime": "GTD",
		"txFeeCoin": "SP$",
		"pair": "BTC-SP$",
		"strike": "7000",
		"amount": "1",
		"unitPremium": "2",
		"expiryDate": "2019-10-04T08:00:00.000Z"
	},
	{
		"action": "SELL",
		"type": "PUT",
		"lifetime": "GTD",
		"txFeeCoin": "SPO",
		"pair": "BTC-SP$",
		"strike": "6000",
		"amount": "2",
		"unitPremium": "2.5",
		"expiryDate": "2019-12-01T08:00:00.000Z"
	}
]'
```

> Example Body

```json
[
	{
		"action": "BUY",
		"type": "PUT",
		"lifetime": "GTD",
		"txFeeCoin": "SP$",
		"pair": "BTC-SP$",
		"strike": "7000",
		"amount": "1",
		"unitPremium": "2",
		"expiryDate": "2019-10-04T08:00:00.000Z"
	},
	{
		"action": "SELL",
		"type": "PUT",
		"lifetime": "GTD",
		"txFeeCoin": "SPO",
		"pair": "BTC-SP$",
		"strike": "6000",
		"amount": "2",
		"unitPremium": "2.5",
		"expiryDate": "2019-12-01T08:00:00.000Z"
	}
]
```


### URL Endpoint
`https://api.sparrowsandbox.com/trades/book/bulkCreate`

### HEADERS
Parameter | Default 
--------- | ------- 
Content-Type | application/json
Authorization | Your Authorization Token
api-key | Your API KEY ID

<!-- END POST - Bulk Create new trade orders with unitPremium -->


```shell
curl --location --request GET 'https://api.sparrowsandbox.com/trades/book'
```

> Example Response

```json
[
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-04T08:00:00.000Z",
    "strike": "8000",
    "call": {
      "totalQuantity": "3",
      "maxBid": {
        "quantity": "1",
        "price": {
          "unitPremium": "307.44",
          "tradeUnitPremium": "30.744",
          "totalPremium": "307.44"
        },
        "impliedVolatility": "119.586292",
        "greeks": {
          "delta": "0.44551539755575087",
          "gamma": "0.0004513544127329389",
          "theta": "-17421.057502665175",
          "vega": "3.2623289499362587"
        }
      },
      "minAsk": null,
      "openInterest": "0"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-04T08:00:00.000Z",
    "strike": "8250",
    "call": {
      "totalQuantity": "1",
      "maxBid": {
        "quantity": "1",
        "price": {
          "unitPremium": "214.17",
          "tradeUnitPremium": "21.417",
          "totalPremium": "214.17"
        },
        "impliedVolatility": "117.992588",
        "greeks": {
          "delta": "0.3493781039763387",
          "gamma": "0.0003587379573724116",
          "theta": "-16101.110834773377",
          "vega": "3.0558761453717715"
        }
      },
      "minAsk": null,
      "openInterest": "0"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-11T08:00:00.000Z",
    "strike": "8500",
    "call": {
      "totalQuantity": "0.1",
      "maxBid": {
        "quantity": "0.1",
        "price": {
          "unitPremium": "244.3",
          "tradeUnitPremium": "24.43",
          "totalPremium": "24.43"
        },
        "impliedVolatility": "92.162149",
        "greeks": {
          "delta": "0.3245546194179445",
          "gamma": "0.00025903867958489233",
          "theta": "-7420.420798469983",
          "vega": "4.89130212111081"
        }
      },
      "minAsk": null,
      "openInterest": "0"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-04T08:00:00.000Z",
    "strike": "9000",
    "call": {
      "totalQuantity": "19.5",
      "maxBid": null,
      "minAsk": {
        "quantity": "19.5",
        "price": {
          "unitPremium": "17.5",
          "tradeUnitPremium": "1.75",
          "totalPremium": "341.25"
        },
        "impliedVolatility": "84.591524",
        "greeks": {
          "delta": "0.06021156730496735",
          "gamma": "0.0000862361693246329",
          "theta": "-3721.4394036662957",
          "vega": "0.985187148023525"
        }
      },
      "openInterest": "0"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-04T08:00:00.000Z",
    "strike": "9750",
    "call": {
      "totalQuantity": "0.1",
      "maxBid": null,
      "minAsk": {
        "quantity": "0.1",
        "price": {
          "unitPremium": "16.63",
          "tradeUnitPremium": "1.663",
          "totalPremium": "1.663"
        },
        "impliedVolatility": "118.826486",
        "greeks": {
          "delta": "0.04344833423026628",
          "gamma": "0.00004429923758647504",
          "theta": "-4039.034919879933",
          "vega": "0.7612003697120275"
        }
      },
      "openInterest": "3"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-04T08:00:00.000Z",
    "strike": "10000",
    "call": {
      "totalQuantity": "0.8",
      "maxBid": {
        "quantity": "0.8",
        "price": {
          "unitPremium": "17.14",
          "tradeUnitPremium": "1.714",
          "totalPremium": "13.712"
        },
        "impliedVolatility": "130.182542",
        "greeks": {
          "delta": "0.04145904158414915",
          "gamma": "0.000038583612420825715",
          "theta": "-4253.108332603115",
          "vega": "0.73162465870199"
        }
      },
      "minAsk": null,
      "openInterest": "0.2"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-04T08:00:00.000Z",
    "strike": "11500",
    "call": {
      "totalQuantity": "1",
      "maxBid": null,
      "minAsk": {
        "quantity": "1",
        "price": {
          "unitPremium": "221.65",
          "tradeUnitPremium": "22.165",
          "totalPremium": "221.65"
        },
        "impliedVolatility": "331.432859",
        "greeks": {
          "delta": "0.17566826271590297",
          "gamma": "0.00006421464969136541",
          "theta": "-31580.401043302005",
          "vega": "2.1338147539141272"
        }
      },
      "openInterest": "0"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-12-27T08:00:00.000Z",
    "strike": "9000",
    "call": {
      "totalQuantity": "0",
      "maxBid": null,
      "minAsk": null,
      "openInterest": "1"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-12-27T08:00:00.000Z",
    "strike": "9250",
    "call": {
      "totalQuantity": "0",
      "maxBid": null,
      "minAsk": null,
      "openInterest": "0.8"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2020-03-27T08:00:00.000Z",
    "strike": "10000",
    "call": {
      "totalQuantity": "0",
      "maxBid": null,
      "minAsk": null,
      "openInterest": "1"
    },
    "put": null
  }
]
```



<!-- END POST - Bulk Create new trade orders with unitPremium -->



## GET - Order Book
```shell
curl --location --request GET 'https://api.sparrowsandbox.com/trades/book'
```

> Example Response

```json
[
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-04T08:00:00.000Z",
    "strike": "8000",
    "call": {
      "totalQuantity": "3",
      "maxBid": {
        "quantity": "1",
        "price": {
          "unitPremium": "307.44",
          "tradeUnitPremium": "30.744",
          "totalPremium": "307.44"
        },
        "impliedVolatility": "119.586292",
        "greeks": {
          "delta": "0.44551539755575087",
          "gamma": "0.0004513544127329389",
          "theta": "-17421.057502665175",
          "vega": "3.2623289499362587"
        }
      },
      "minAsk": null,
      "openInterest": "0"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-04T08:00:00.000Z",
    "strike": "8250",
    "call": {
      "totalQuantity": "1",
      "maxBid": {
        "quantity": "1",
        "price": {
          "unitPremium": "214.17",
          "tradeUnitPremium": "21.417",
          "totalPremium": "214.17"
        },
        "impliedVolatility": "117.992588",
        "greeks": {
          "delta": "0.3493781039763387",
          "gamma": "0.0003587379573724116",
          "theta": "-16101.110834773377",
          "vega": "3.0558761453717715"
        }
      },
      "minAsk": null,
      "openInterest": "0"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-11T08:00:00.000Z",
    "strike": "8500",
    "call": {
      "totalQuantity": "0.1",
      "maxBid": {
        "quantity": "0.1",
        "price": {
          "unitPremium": "244.3",
          "tradeUnitPremium": "24.43",
          "totalPremium": "24.43"
        },
        "impliedVolatility": "92.162149",
        "greeks": {
          "delta": "0.3245546194179445",
          "gamma": "0.00025903867958489233",
          "theta": "-7420.420798469983",
          "vega": "4.89130212111081"
        }
      },
      "minAsk": null,
      "openInterest": "0"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-04T08:00:00.000Z",
    "strike": "9000",
    "call": {
      "totalQuantity": "19.5",
      "maxBid": null,
      "minAsk": {
        "quantity": "19.5",
        "price": {
          "unitPremium": "17.5",
          "tradeUnitPremium": "1.75",
          "totalPremium": "341.25"
        },
        "impliedVolatility": "84.591524",
        "greeks": {
          "delta": "0.06021156730496735",
          "gamma": "0.0000862361693246329",
          "theta": "-3721.4394036662957",
          "vega": "0.985187148023525"
        }
      },
      "openInterest": "0"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-04T08:00:00.000Z",
    "strike": "9750",
    "call": {
      "totalQuantity": "0.1",
      "maxBid": null,
      "minAsk": {
        "quantity": "0.1",
        "price": {
          "unitPremium": "16.63",
          "tradeUnitPremium": "1.663",
          "totalPremium": "1.663"
        },
        "impliedVolatility": "118.826486",
        "greeks": {
          "delta": "0.04344833423026628",
          "gamma": "0.00004429923758647504",
          "theta": "-4039.034919879933",
          "vega": "0.7612003697120275"
        }
      },
      "openInterest": "3"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-04T08:00:00.000Z",
    "strike": "10000",
    "call": {
      "totalQuantity": "0.8",
      "maxBid": {
        "quantity": "0.8",
        "price": {
          "unitPremium": "17.14",
          "tradeUnitPremium": "1.714",
          "totalPremium": "13.712"
        },
        "impliedVolatility": "130.182542",
        "greeks": {
          "delta": "0.04145904158414915",
          "gamma": "0.000038583612420825715",
          "theta": "-4253.108332603115",
          "vega": "0.73162465870199"
        }
      },
      "minAsk": null,
      "openInterest": "0.2"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-04T08:00:00.000Z",
    "strike": "11500",
    "call": {
      "totalQuantity": "1",
      "maxBid": null,
      "minAsk": {
        "quantity": "1",
        "price": {
          "unitPremium": "221.65",
          "tradeUnitPremium": "22.165",
          "totalPremium": "221.65"
        },
        "impliedVolatility": "331.432859",
        "greeks": {
          "delta": "0.17566826271590297",
          "gamma": "0.00006421464969136541",
          "theta": "-31580.401043302005",
          "vega": "2.1338147539141272"
        }
      },
      "openInterest": "0"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-12-27T08:00:00.000Z",
    "strike": "9000",
    "call": {
      "totalQuantity": "0",
      "maxBid": null,
      "minAsk": null,
      "openInterest": "1"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-12-27T08:00:00.000Z",
    "strike": "9250",
    "call": {
      "totalQuantity": "0",
      "maxBid": null,
      "minAsk": null,
      "openInterest": "0.8"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2020-03-27T08:00:00.000Z",
    "strike": "10000",
    "call": {
      "totalQuantity": "0",
      "maxBid": null,
      "minAsk": null,
      "openInterest": "1"
    },
    "put": null
  }
]
```


### URL Endpoint
`https://api.sparrowsandbox.com/trades/book`


### HEADERS
Parameter | Default 
--------- | ------- 
Authorization | Your Authorization Token
api-key | Your API KEY ID


<!-- END GET - Order Book-->

## GET - Order Book For Pair
```shell
curl --location --request GET 'https://api.sparrowsandbox.com/trades/book/BTC-SP$'
```
> Example Response

```json
[
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-04T08:00:00.000Z",
    "strike": "8000",
    "call": {
      "totalQuantity": "3",
      "maxBid": {
        "quantity": "1",
        "price": {
          "unitPremium": "307.44",
          "tradeUnitPremium": "30.744",
          "totalPremium": "307.44"
        },
        "impliedVolatility": "119.586292",
        "greeks": {
          "delta": "0.44551539755575087",
          "gamma": "0.0004513544127329389",
          "theta": "-17421.057502665175",
          "vega": "3.2623289499362587"
        }
      },
      "minAsk": null,
      "openInterest": "0"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-04T08:00:00.000Z",
    "strike": "8250",
    "call": {
      "totalQuantity": "1",
      "maxBid": {
        "quantity": "1",
        "price": {
          "unitPremium": "214.17",
          "tradeUnitPremium": "21.417",
          "totalPremium": "214.17"
        },
        "impliedVolatility": "117.992588",
        "greeks": {
          "delta": "0.3493781039763387",
          "gamma": "0.0003587379573724116",
          "theta": "-16101.110834773377",
          "vega": "3.0558761453717715"
        }
      },
      "minAsk": null,
      "openInterest": "0"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-11T08:00:00.000Z",
    "strike": "8500",
    "call": {
      "totalQuantity": "0.1",
      "maxBid": {
        "quantity": "0.1",
        "price": {
          "unitPremium": "244.3",
          "tradeUnitPremium": "24.43",
          "totalPremium": "24.43"
        },
        "impliedVolatility": "92.162149",
        "greeks": {
          "delta": "0.3245546194179445",
          "gamma": "0.00025903867958489233",
          "theta": "-7420.420798469983",
          "vega": "4.89130212111081"
        }
      },
      "minAsk": null,
      "openInterest": "0"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-04T08:00:00.000Z",
    "strike": "9000",
    "call": {
      "totalQuantity": "19.5",
      "maxBid": null,
      "minAsk": {
        "quantity": "19.5",
        "price": {
          "unitPremium": "17.5",
          "tradeUnitPremium": "1.75",
          "totalPremium": "341.25"
        },
        "impliedVolatility": "84.591524",
        "greeks": {
          "delta": "0.06021156730496735",
          "gamma": "0.0000862361693246329",
          "theta": "-3721.4394036662957",
          "vega": "0.985187148023525"
        }
      },
      "openInterest": "0"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-04T08:00:00.000Z",
    "strike": "9750",
    "call": {
      "totalQuantity": "0.1",
      "maxBid": null,
      "minAsk": {
        "quantity": "0.1",
        "price": {
          "unitPremium": "16.63",
          "tradeUnitPremium": "1.663",
          "totalPremium": "1.663"
        },
        "impliedVolatility": "118.826486",
        "greeks": {
          "delta": "0.04344833423026628",
          "gamma": "0.00004429923758647504",
          "theta": "-4039.034919879933",
          "vega": "0.7612003697120275"
        }
      },
      "openInterest": "3"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-04T08:00:00.000Z",
    "strike": "10000",
    "call": {
      "totalQuantity": "0.8",
      "maxBid": {
        "quantity": "0.8",
        "price": {
          "unitPremium": "17.14",
          "tradeUnitPremium": "1.714",
          "totalPremium": "13.712"
        },
        "impliedVolatility": "130.182542",
        "greeks": {
          "delta": "0.04145904158414915",
          "gamma": "0.000038583612420825715",
          "theta": "-4253.108332603115",
          "vega": "0.73162465870199"
        }
      },
      "minAsk": null,
      "openInterest": "0.2"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-04T08:00:00.000Z",
    "strike": "11500",
    "call": {
      "totalQuantity": "1",
      "maxBid": null,
      "minAsk": {
        "quantity": "1",
        "price": {
          "unitPremium": "221.65",
          "tradeUnitPremium": "22.165",
          "totalPremium": "221.65"
        },
        "impliedVolatility": "331.432859",
        "greeks": {
          "delta": "0.17566826271590297",
          "gamma": "0.00006421464969136541",
          "theta": "-31580.401043302005",
          "vega": "2.1338147539141272"
        }
      },
      "openInterest": "0"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-12-27T08:00:00.000Z",
    "strike": "9000",
    "call": {
      "totalQuantity": "0",
      "maxBid": null,
      "minAsk": null,
      "openInterest": "1"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-12-27T08:00:00.000Z",
    "strike": "9250",
    "call": {
      "totalQuantity": "0",
      "maxBid": null,
      "minAsk": null,
      "openInterest": "0.8"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2020-03-27T08:00:00.000Z",
    "strike": "10000",
    "call": {
      "totalQuantity": "0",
      "maxBid": null,
      "minAsk": null,
      "openInterest": "1"
    },
    "put": null
  }
]
```


### URL Endpoint
`https://api.sparrowsandbox.com/trades/book/BTC-SP$`



<!-- END GET - Order Book For Pair-->

## GET - Order Book Filter By Type
```shell
curl --location --request GET 'https://api.sparrowsandbox.com/trades/book/BTC-SP$?type=call'
```

> Example Response

```json
[
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-04T08:00:00.000Z",
    "strike": "8000",
    "call": {
      "totalQuantity": "3",
      "maxBid": {
        "quantity": "1",
        "price": {
          "unitPremium": "307.44",
          "tradeUnitPremium": "30.744",
          "totalPremium": "307.44"
        },
        "impliedVolatility": "119.586292",
        "greeks": {
          "delta": "0.44551539755575087",
          "gamma": "0.0004513544127329389",
          "theta": "-17421.057502665175",
          "vega": "3.2623289499362587"
        }
      },
      "minAsk": null,
      "openInterest": "0"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-04T08:00:00.000Z",
    "strike": "8250",
    "call": {
      "totalQuantity": "1",
      "maxBid": {
        "quantity": "1",
        "price": {
          "unitPremium": "214.17",
          "tradeUnitPremium": "21.417",
          "totalPremium": "214.17"
        },
        "impliedVolatility": "117.992588",
        "greeks": {
          "delta": "0.3493781039763387",
          "gamma": "0.0003587379573724116",
          "theta": "-16101.110834773377",
          "vega": "3.0558761453717715"
        }
      },
      "minAsk": null,
      "openInterest": "0"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-11T08:00:00.000Z",
    "strike": "8500",
    "call": {
      "totalQuantity": "0.1",
      "maxBid": {
        "quantity": "0.1",
        "price": {
          "unitPremium": "244.3",
          "tradeUnitPremium": "24.43",
          "totalPremium": "24.43"
        },
        "impliedVolatility": "92.162149",
        "greeks": {
          "delta": "0.3245546194179445",
          "gamma": "0.00025903867958489233",
          "theta": "-7420.420798469983",
          "vega": "4.89130212111081"
        }
      },
      "minAsk": null,
      "openInterest": "0"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-04T08:00:00.000Z",
    "strike": "9000",
    "call": {
      "totalQuantity": "19.5",
      "maxBid": null,
      "minAsk": {
        "quantity": "19.5",
        "price": {
          "unitPremium": "17.5",
          "tradeUnitPremium": "1.75",
          "totalPremium": "341.25"
        },
        "impliedVolatility": "84.591524",
        "greeks": {
          "delta": "0.06021156730496735",
          "gamma": "0.0000862361693246329",
          "theta": "-3721.4394036662957",
          "vega": "0.985187148023525"
        }
      },
      "openInterest": "0"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-04T08:00:00.000Z",
    "strike": "9750",
    "call": {
      "totalQuantity": "0.1",
      "maxBid": null,
      "minAsk": {
        "quantity": "0.1",
        "price": {
          "unitPremium": "16.63",
          "tradeUnitPremium": "1.663",
          "totalPremium": "1.663"
        },
        "impliedVolatility": "118.826486",
        "greeks": {
          "delta": "0.04344833423026628",
          "gamma": "0.00004429923758647504",
          "theta": "-4039.034919879933",
          "vega": "0.7612003697120275"
        }
      },
      "openInterest": "3"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-04T08:00:00.000Z",
    "strike": "10000",
    "call": {
      "totalQuantity": "0.8",
      "maxBid": {
        "quantity": "0.8",
        "price": {
          "unitPremium": "17.14",
          "tradeUnitPremium": "1.714",
          "totalPremium": "13.712"
        },
        "impliedVolatility": "130.182542",
        "greeks": {
          "delta": "0.04145904158414915",
          "gamma": "0.000038583612420825715",
          "theta": "-4253.108332603115",
          "vega": "0.73162465870199"
        }
      },
      "minAsk": null,
      "openInterest": "0.2"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-04T08:00:00.000Z",
    "strike": "11500",
    "call": {
      "totalQuantity": "1",
      "maxBid": null,
      "minAsk": {
        "quantity": "1",
        "price": {
          "unitPremium": "221.65",
          "tradeUnitPremium": "22.165",
          "totalPremium": "221.65"
        },
        "impliedVolatility": "331.432859",
        "greeks": {
          "delta": "0.17566826271590297",
          "gamma": "0.00006421464969136541",
          "theta": "-31580.401043302005",
          "vega": "2.1338147539141272"
        }
      },
      "openInterest": "0"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-12-27T08:00:00.000Z",
    "strike": "9000",
    "call": {
      "totalQuantity": "0",
      "maxBid": null,
      "minAsk": null,
      "openInterest": "1"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-12-27T08:00:00.000Z",
    "strike": "9250",
    "call": {
      "totalQuantity": "0",
      "maxBid": null,
      "minAsk": null,
      "openInterest": "0.8"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2020-03-27T08:00:00.000Z",
    "strike": "10000",
    "call": {
      "totalQuantity": "0",
      "maxBid": null,
      "minAsk": null,
      "openInterest": "1"
    },
    "put": null
  }
]
```


### URL Endpoint
`https://api.sparrowsandbox.com/trades/book/:pair?type={{type}}`

### PARAMS
Parameter |  type
--------- | ------- 
type | {{type}} CALL/PUT

### PATH VARIABLE
Parameter | value
--------- | ------- 
pair | BTC/SP$


<!-- END GET - Order Book Filter By Type-->

## GET - Order Book Filter By Strike
```shell
curl --location --request GET 'https://api.sparrowsandbox.com/trades/book/BTC-SP$?minStrike=8000&maxStrike=10000'

```

> Example Response

```json
[
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-04T08:00:00.000Z",
    "strike": "8000",
    "call": {
      "totalQuantity": "3",
      "maxBid": {
        "quantity": "1",
        "price": {
          "unitPremium": "307.44",
          "tradeUnitPremium": "30.744",
          "totalPremium": "307.44"
        },
        "impliedVolatility": "119.586292",
        "greeks": {
          "delta": "0.44551539755575087",
          "gamma": "0.0004513544127329389",
          "theta": "-17421.057502665175",
          "vega": "3.2623289499362587"
        }
      },
      "minAsk": null,
      "openInterest": "0"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-04T08:00:00.000Z",
    "strike": "8250",
    "call": {
      "totalQuantity": "1",
      "maxBid": {
        "quantity": "1",
        "price": {
          "unitPremium": "214.17",
          "tradeUnitPremium": "21.417",
          "totalPremium": "214.17"
        },
        "impliedVolatility": "117.992588",
        "greeks": {
          "delta": "0.3493781039763387",
          "gamma": "0.0003587379573724116",
          "theta": "-16101.110834773377",
          "vega": "3.0558761453717715"
        }
      },
      "minAsk": null,
      "openInterest": "0"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-11T08:00:00.000Z",
    "strike": "8500",
    "call": {
      "totalQuantity": "0.1",
      "maxBid": {
        "quantity": "0.1",
        "price": {
          "unitPremium": "244.3",
          "tradeUnitPremium": "24.43",
          "totalPremium": "24.43"
        },
        "impliedVolatility": "92.162149",
        "greeks": {
          "delta": "0.3245546194179445",
          "gamma": "0.00025903867958489233",
          "theta": "-7420.420798469983",
          "vega": "4.89130212111081"
        }
      },
      "minAsk": null,
      "openInterest": "0"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-04T08:00:00.000Z",
    "strike": "9000",
    "call": {
      "totalQuantity": "19.5",
      "maxBid": null,
      "minAsk": {
        "quantity": "19.5",
        "price": {
          "unitPremium": "17.5",
          "tradeUnitPremium": "1.75",
          "totalPremium": "341.25"
        },
        "impliedVolatility": "84.591524",
        "greeks": {
          "delta": "0.06021156730496735",
          "gamma": "0.0000862361693246329",
          "theta": "-3721.4394036662957",
          "vega": "0.985187148023525"
        }
      },
      "openInterest": "0"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-04T08:00:00.000Z",
    "strike": "9750",
    "call": {
      "totalQuantity": "0.1",
      "maxBid": null,
      "minAsk": {
        "quantity": "0.1",
        "price": {
          "unitPremium": "16.63",
          "tradeUnitPremium": "1.663",
          "totalPremium": "1.663"
        },
        "impliedVolatility": "118.826486",
        "greeks": {
          "delta": "0.04344833423026628",
          "gamma": "0.00004429923758647504",
          "theta": "-4039.034919879933",
          "vega": "0.7612003697120275"
        }
      },
      "openInterest": "3"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-04T08:00:00.000Z",
    "strike": "10000",
    "call": {
      "totalQuantity": "0.8",
      "maxBid": {
        "quantity": "0.8",
        "price": {
          "unitPremium": "17.14",
          "tradeUnitPremium": "1.714",
          "totalPremium": "13.712"
        },
        "impliedVolatility": "130.182542",
        "greeks": {
          "delta": "0.04145904158414915",
          "gamma": "0.000038583612420825715",
          "theta": "-4253.108332603115",
          "vega": "0.73162465870199"
        }
      },
      "minAsk": null,
      "openInterest": "0.2"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-04T08:00:00.000Z",
    "strike": "11500",
    "call": {
      "totalQuantity": "1",
      "maxBid": null,
      "minAsk": {
        "quantity": "1",
        "price": {
          "unitPremium": "221.65",
          "tradeUnitPremium": "22.165",
          "totalPremium": "221.65"
        },
        "impliedVolatility": "331.432859",
        "greeks": {
          "delta": "0.17566826271590297",
          "gamma": "0.00006421464969136541",
          "theta": "-31580.401043302005",
          "vega": "2.1338147539141272"
        }
      },
      "openInterest": "0"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-12-27T08:00:00.000Z",
    "strike": "9000",
    "call": {
      "totalQuantity": "0",
      "maxBid": null,
      "minAsk": null,
      "openInterest": "1"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-12-27T08:00:00.000Z",
    "strike": "9250",
    "call": {
      "totalQuantity": "0",
      "maxBid": null,
      "minAsk": null,
      "openInterest": "0.8"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2020-03-27T08:00:00.000Z",
    "strike": "10000",
    "call": {
      "totalQuantity": "0",
      "maxBid": null,
      "minAsk": null,
      "openInterest": "1"
    },
    "put": null
  }
]
```


### URL Endpoint
`https://api.sparrowsandbox.com/trades/book/:pair?minStrike=8000&maxStrike=10000`

### PARAMS
Parameter |  value
--------- | ------- 
minStrike | 8000
maxStrike | 10000

### PATH VARIABLE
Parameter | value
--------- | ------- 
pair | BTC/SP$


<!-- END GET - Order Book For Strike-->

## GET - Order Book Filter By Expiry
```shell
curl --location --request GET 'https://api.sparrowsandbox.com/trades/book/BTC-SP$?minExpiry=2019-10-02T02:00:00.000Z&maxExpiry=2019-11-11T08:00:00.000Z'
```

> Example Response

```json
[
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-04T08:00:00.000Z",
    "strike": "8000",
    "call": {
      "totalQuantity": "3",
      "maxBid": {
        "quantity": "1",
        "price": {
          "unitPremium": "307.44",
          "tradeUnitPremium": "30.744",
          "totalPremium": "307.44"
        },
        "impliedVolatility": "119.586292",
        "greeks": {
          "delta": "0.44551539755575087",
          "gamma": "0.0004513544127329389",
          "theta": "-17421.057502665175",
          "vega": "3.2623289499362587"
        }
      },
      "minAsk": null,
      "openInterest": "0"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-04T08:00:00.000Z",
    "strike": "8250",
    "call": {
      "totalQuantity": "1",
      "maxBid": {
        "quantity": "1",
        "price": {
          "unitPremium": "214.17",
          "tradeUnitPremium": "21.417",
          "totalPremium": "214.17"
        },
        "impliedVolatility": "117.992588",
        "greeks": {
          "delta": "0.3493781039763387",
          "gamma": "0.0003587379573724116",
          "theta": "-16101.110834773377",
          "vega": "3.0558761453717715"
        }
      },
      "minAsk": null,
      "openInterest": "0"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-11T08:00:00.000Z",
    "strike": "8500",
    "call": {
      "totalQuantity": "0.1",
      "maxBid": {
        "quantity": "0.1",
        "price": {
          "unitPremium": "244.3",
          "tradeUnitPremium": "24.43",
          "totalPremium": "24.43"
        },
        "impliedVolatility": "92.162149",
        "greeks": {
          "delta": "0.3245546194179445",
          "gamma": "0.00025903867958489233",
          "theta": "-7420.420798469983",
          "vega": "4.89130212111081"
        }
      },
      "minAsk": null,
      "openInterest": "0"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-04T08:00:00.000Z",
    "strike": "9000",
    "call": {
      "totalQuantity": "19.5",
      "maxBid": null,
      "minAsk": {
        "quantity": "19.5",
        "price": {
          "unitPremium": "17.5",
          "tradeUnitPremium": "1.75",
          "totalPremium": "341.25"
        },
        "impliedVolatility": "84.591524",
        "greeks": {
          "delta": "0.06021156730496735",
          "gamma": "0.0000862361693246329",
          "theta": "-3721.4394036662957",
          "vega": "0.985187148023525"
        }
      },
      "openInterest": "0"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-04T08:00:00.000Z",
    "strike": "9750",
    "call": {
      "totalQuantity": "0.1",
      "maxBid": null,
      "minAsk": {
        "quantity": "0.1",
        "price": {
          "unitPremium": "16.63",
          "tradeUnitPremium": "1.663",
          "totalPremium": "1.663"
        },
        "impliedVolatility": "118.826486",
        "greeks": {
          "delta": "0.04344833423026628",
          "gamma": "0.00004429923758647504",
          "theta": "-4039.034919879933",
          "vega": "0.7612003697120275"
        }
      },
      "openInterest": "3"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-04T08:00:00.000Z",
    "strike": "10000",
    "call": {
      "totalQuantity": "0.8",
      "maxBid": {
        "quantity": "0.8",
        "price": {
          "unitPremium": "17.14",
          "tradeUnitPremium": "1.714",
          "totalPremium": "13.712"
        },
        "impliedVolatility": "130.182542",
        "greeks": {
          "delta": "0.04145904158414915",
          "gamma": "0.000038583612420825715",
          "theta": "-4253.108332603115",
          "vega": "0.73162465870199"
        }
      },
      "minAsk": null,
      "openInterest": "0.2"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-04T08:00:00.000Z",
    "strike": "11500",
    "call": {
      "totalQuantity": "1",
      "maxBid": null,
      "minAsk": {
        "quantity": "1",
        "price": {
          "unitPremium": "221.65",
          "tradeUnitPremium": "22.165",
          "totalPremium": "221.65"
        },
        "impliedVolatility": "331.432859",
        "greeks": {
          "delta": "0.17566826271590297",
          "gamma": "0.00006421464969136541",
          "theta": "-31580.401043302005",
          "vega": "2.1338147539141272"
        }
      },
      "openInterest": "0"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-12-27T08:00:00.000Z",
    "strike": "9000",
    "call": {
      "totalQuantity": "0",
      "maxBid": null,
      "minAsk": null,
      "openInterest": "1"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-12-27T08:00:00.000Z",
    "strike": "9250",
    "call": {
      "totalQuantity": "0",
      "maxBid": null,
      "minAsk": null,
      "openInterest": "0.8"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2020-03-27T08:00:00.000Z",
    "strike": "10000",
    "call": {
      "totalQuantity": "0",
      "maxBid": null,
      "minAsk": null,
      "openInterest": "1"
    },
    "put": null
  }
]
```


### URL Endpoint
`https://api.sparrowsandbox.com/trades/book/:pair?minStrike=8000&maxStrike=10000`

### PARAMS
Parameter |  value
--------- | ------- 
minExpiry | 2019-10-02T02:00:00.000Z <- date in ISO String
maxExpiry | 2019-11-11T08:00:00.000Z <- date in ISO String


### PATH VARIABLE
Parameter | value
--------- | ------- 
pair | BTC/SP$


<!-- END GET - Order Book filter by Expiry -->

## GET - Order Book Depth
```shell
curl --location --request GET 'https://api.sparrowsandbox.com/trades/book/depth/:pair?type=call&strike=8000&expiry=2019-10-11T08:00:00.000Z'
```

> Example Response

```json
[
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-04T08:00:00.000Z",
    "strike": "8000",
    "call": {
      "totalQuantity": "3",
      "maxBid": {
        "quantity": "1",
        "price": {
          "unitPremium": "307.44",
          "tradeUnitPremium": "30.744",
          "totalPremium": "307.44"
        },
        "impliedVolatility": "119.586292",
        "greeks": {
          "delta": "0.44551539755575087",
          "gamma": "0.0004513544127329389",
          "theta": "-17421.057502665175",
          "vega": "3.2623289499362587"
        }
      },
      "minAsk": null,
      "openInterest": "0"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-04T08:00:00.000Z",
    "strike": "8250",
    "call": {
      "totalQuantity": "1",
      "maxBid": {
        "quantity": "1",
        "price": {
          "unitPremium": "214.17",
          "tradeUnitPremium": "21.417",
          "totalPremium": "214.17"
        },
        "impliedVolatility": "117.992588",
        "greeks": {
          "delta": "0.3493781039763387",
          "gamma": "0.0003587379573724116",
          "theta": "-16101.110834773377",
          "vega": "3.0558761453717715"
        }
      },
      "minAsk": null,
      "openInterest": "0"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-11T08:00:00.000Z",
    "strike": "8500",
    "call": {
      "totalQuantity": "0.1",
      "maxBid": {
        "quantity": "0.1",
        "price": {
          "unitPremium": "244.3",
          "tradeUnitPremium": "24.43",
          "totalPremium": "24.43"
        },
        "impliedVolatility": "92.162149",
        "greeks": {
          "delta": "0.3245546194179445",
          "gamma": "0.00025903867958489233",
          "theta": "-7420.420798469983",
          "vega": "4.89130212111081"
        }
      },
      "minAsk": null,
      "openInterest": "0"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-04T08:00:00.000Z",
    "strike": "9000",
    "call": {
      "totalQuantity": "19.5",
      "maxBid": null,
      "minAsk": {
        "quantity": "19.5",
        "price": {
          "unitPremium": "17.5",
          "tradeUnitPremium": "1.75",
          "totalPremium": "341.25"
        },
        "impliedVolatility": "84.591524",
        "greeks": {
          "delta": "0.06021156730496735",
          "gamma": "0.0000862361693246329",
          "theta": "-3721.4394036662957",
          "vega": "0.985187148023525"
        }
      },
      "openInterest": "0"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-04T08:00:00.000Z",
    "strike": "9750",
    "call": {
      "totalQuantity": "0.1",
      "maxBid": null,
      "minAsk": {
        "quantity": "0.1",
        "price": {
          "unitPremium": "16.63",
          "tradeUnitPremium": "1.663",
          "totalPremium": "1.663"
        },
        "impliedVolatility": "118.826486",
        "greeks": {
          "delta": "0.04344833423026628",
          "gamma": "0.00004429923758647504",
          "theta": "-4039.034919879933",
          "vega": "0.7612003697120275"
        }
      },
      "openInterest": "3"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-04T08:00:00.000Z",
    "strike": "10000",
    "call": {
      "totalQuantity": "0.8",
      "maxBid": {
        "quantity": "0.8",
        "price": {
          "unitPremium": "17.14",
          "tradeUnitPremium": "1.714",
          "totalPremium": "13.712"
        },
        "impliedVolatility": "130.182542",
        "greeks": {
          "delta": "0.04145904158414915",
          "gamma": "0.000038583612420825715",
          "theta": "-4253.108332603115",
          "vega": "0.73162465870199"
        }
      },
      "minAsk": null,
      "openInterest": "0.2"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-04T08:00:00.000Z",
    "strike": "11500",
    "call": {
      "totalQuantity": "1",
      "maxBid": null,
      "minAsk": {
        "quantity": "1",
        "price": {
          "unitPremium": "221.65",
          "tradeUnitPremium": "22.165",
          "totalPremium": "221.65"
        },
        "impliedVolatility": "331.432859",
        "greeks": {
          "delta": "0.17566826271590297",
          "gamma": "0.00006421464969136541",
          "theta": "-31580.401043302005",
          "vega": "2.1338147539141272"
        }
      },
      "openInterest": "0"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-12-27T08:00:00.000Z",
    "strike": "9000",
    "call": {
      "totalQuantity": "0",
      "maxBid": null,
      "minAsk": null,
      "openInterest": "1"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-12-27T08:00:00.000Z",
    "strike": "9250",
    "call": {
      "totalQuantity": "0",
      "maxBid": null,
      "minAsk": null,
      "openInterest": "0.8"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2020-03-27T08:00:00.000Z",
    "strike": "10000",
    "call": {
      "totalQuantity": "0",
      "maxBid": null,
      "minAsk": null,
      "openInterest": "1"
    },
    "put": null
  }
]
```


### URL Endpoint
`https://api.sparrowsandbox.com/trades/book/depth/:pair?type=call&strike=8000&expiry=2019-10-11T08:00:00.000Z`

### PARAMS
Parameter |  value
--------- | ------- 
type      | Call
strike | 8000
expiry | 2019-10-11T08:00:00.000Z


### PATH VARIABLE
Parameter | value
--------- | ------- 
pair | BTC/SP$


<!-- END GET - Order Book depth -->

## GET - Order Book Depth - Filter By Action
```shell
curl --location --request GET 'https://api.sparrowsandbox.com/trades/book/BTC-SP$?action=BUY'
```

> Example Response

```json
[
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-04T08:00:00.000Z",
    "strike": "8000",
    "call": {
      "totalQuantity": "3",
      "maxBid": {
        "quantity": "1",
        "price": {
          "unitPremium": "307.44",
          "tradeUnitPremium": "30.744",
          "totalPremium": "307.44"
        },
        "impliedVolatility": "119.586292",
        "greeks": {
          "delta": "0.44551539755575087",
          "gamma": "0.0004513544127329389",
          "theta": "-17421.057502665175",
          "vega": "3.2623289499362587"
        }
      },
      "minAsk": null,
      "openInterest": "0"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-04T08:00:00.000Z",
    "strike": "8250",
    "call": {
      "totalQuantity": "1",
      "maxBid": {
        "quantity": "1",
        "price": {
          "unitPremium": "214.17",
          "tradeUnitPremium": "21.417",
          "totalPremium": "214.17"
        },
        "impliedVolatility": "117.992588",
        "greeks": {
          "delta": "0.3493781039763387",
          "gamma": "0.0003587379573724116",
          "theta": "-16101.110834773377",
          "vega": "3.0558761453717715"
        }
      },
      "minAsk": null,
      "openInterest": "0"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-11T08:00:00.000Z",
    "strike": "8500",
    "call": {
      "totalQuantity": "0.1",
      "maxBid": {
        "quantity": "0.1",
        "price": {
          "unitPremium": "244.3",
          "tradeUnitPremium": "24.43",
          "totalPremium": "24.43"
        },
        "impliedVolatility": "92.162149",
        "greeks": {
          "delta": "0.3245546194179445",
          "gamma": "0.00025903867958489233",
          "theta": "-7420.420798469983",
          "vega": "4.89130212111081"
        }
      },
      "minAsk": null,
      "openInterest": "0"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-04T08:00:00.000Z",
    "strike": "9000",
    "call": {
      "totalQuantity": "19.5",
      "maxBid": null,
      "minAsk": {
        "quantity": "19.5",
        "price": {
          "unitPremium": "17.5",
          "tradeUnitPremium": "1.75",
          "totalPremium": "341.25"
        },
        "impliedVolatility": "84.591524",
        "greeks": {
          "delta": "0.06021156730496735",
          "gamma": "0.0000862361693246329",
          "theta": "-3721.4394036662957",
          "vega": "0.985187148023525"
        }
      },
      "openInterest": "0"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-04T08:00:00.000Z",
    "strike": "9750",
    "call": {
      "totalQuantity": "0.1",
      "maxBid": null,
      "minAsk": {
        "quantity": "0.1",
        "price": {
          "unitPremium": "16.63",
          "tradeUnitPremium": "1.663",
          "totalPremium": "1.663"
        },
        "impliedVolatility": "118.826486",
        "greeks": {
          "delta": "0.04344833423026628",
          "gamma": "0.00004429923758647504",
          "theta": "-4039.034919879933",
          "vega": "0.7612003697120275"
        }
      },
      "openInterest": "3"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-04T08:00:00.000Z",
    "strike": "10000",
    "call": {
      "totalQuantity": "0.8",
      "maxBid": {
        "quantity": "0.8",
        "price": {
          "unitPremium": "17.14",
          "tradeUnitPremium": "1.714",
          "totalPremium": "13.712"
        },
        "impliedVolatility": "130.182542",
        "greeks": {
          "delta": "0.04145904158414915",
          "gamma": "0.000038583612420825715",
          "theta": "-4253.108332603115",
          "vega": "0.73162465870199"
        }
      },
      "minAsk": null,
      "openInterest": "0.2"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-10-04T08:00:00.000Z",
    "strike": "11500",
    "call": {
      "totalQuantity": "1",
      "maxBid": null,
      "minAsk": {
        "quantity": "1",
        "price": {
          "unitPremium": "221.65",
          "tradeUnitPremium": "22.165",
          "totalPremium": "221.65"
        },
        "impliedVolatility": "331.432859",
        "greeks": {
          "delta": "0.17566826271590297",
          "gamma": "0.00006421464969136541",
          "theta": "-31580.401043302005",
          "vega": "2.1338147539141272"
        }
      },
      "openInterest": "0"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-12-27T08:00:00.000Z",
    "strike": "9000",
    "call": {
      "totalQuantity": "0",
      "maxBid": null,
      "minAsk": null,
      "openInterest": "1"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2019-12-27T08:00:00.000Z",
    "strike": "9250",
    "call": {
      "totalQuantity": "0",
      "maxBid": null,
      "minAsk": null,
      "openInterest": "0.8"
    },
    "put": null
  },
  {
    "pair": "BTC-SP$",
    "expiry": "2020-03-27T08:00:00.000Z",
    "strike": "10000",
    "call": {
      "totalQuantity": "0",
      "maxBid": null,
      "minAsk": null,
      "openInterest": "1"
    },
    "put": null
  }
]
```


### URL Endpoint
`https://api.sparrowsandbox.com/trades/book/:pair?action=BUY`

### PARAMS
Parameter |  value
--------- | ------- 
action      | Buy


### PATH VARIABLE
Parameter | value
--------- | ------- 
pair | BTC/SP$


<!-- END GET - Order Book depth Filter by Action-->


## GET - Display all own trades
```shell
curl --location --request GET 'https://api.sparrowsandbox.com/trades/book/own' \
--header 'Authorization: Your Authorization Token' \
--header 'api-key: Your API Key ID'
```

> Example Response

```json
[
  {
    "id": "bd3335ea-90a4-4958-86a0-5ac800b2f767",
    "action": "BUY",
    "type": "CALL",
    "lifetime": "GTD",
    "strike": "8500",
    "amount": {
      "coin": "BTC",
      "amount": "0.1"
    },
    "unfilled": {
      "coin": "BTC",
      "amount": "0.1"
    },
    "premium": {
      "unitPremium": "244.3",
      "tradeUnitPremium": "24.43",
      "totalPremium": "24.43"
    },
    "asset": "BTC",
    "currency": "SP$",
    "createdAt": "2019-09-30T05:54:04.687Z",
    "expiry": "2019-10-11T08:00:00.000Z",
    "status": "BOOKED",
    "locked": {
      "txFee": {
        "coin": "SP$",
        "amount": "0.780946",
        "sp$Equivalent": "0.780946"
      },
      "tradeLock": null,
      "premium": {
        "unitPremium": "244.3",
        "tradeUnitPremium": "24.43",
        "totalPremium": "24.43"
      }
    },
    "matched": {
      "amount": null,
      "payoff": null,
      "tradeLock": null,
      "tradeRelease": null,
      "premium": null
    },
    "contracts": [],
    "orderType": "PREMIUM",
    "impliedVolatility": "0.92693938"
  },
  {
    "id": "73148dac-ebb7-4c65-85a2-cb37e2e88679",
    "action": "SELL",
    "type": "PUT",
    "lifetime": "GTC",
    "strike": "8000",
    "amount": {
      "coin": "BTC",
      "amount": "0.1"
    },
    "unfilled": {
      "coin": "BTC",
      "amount": "0.1"
    },
    "premium": {
      "unitPremium": "365.24",
      "tradeUnitPremium": "36.524",
      "totalPremium": "36.524"
    },
    "asset": "BTC",
    "currency": "SP$",
    "createdAt": "2019-09-25T07:27:28.936Z",
    "expiry": "2019-10-04T08:00:00.000Z",
    "status": "CANCELED",
    "locked": {
      "txFee": null,
      "tradeLock": null,
      "premium": null
    },
    "matched": {
      "amount": null,
      "payoff": null,
      "tradeLock": null,
      "tradeRelease": null,
      "premium": null
    },
    "contracts": [],
    "orderType": "PREMIUM",
    "impliedVolatility": "1.078306"
  }
]

```


### URL Endpoint
`https://api.sparrowsandbox.com/trades/book/own`

### HEADERS
Parameter |  value
--------- | ------- 
Authorization | Your authorization key
api-key | Your API Key ID



<!-- END GET - Order Book depth Filter by Action-->


## GET - Display all own trades - custom
```shell
curl --location --request GET 'https://api.sparrowsandbox.com/trades/book/own?orderby=expiry&order=asc' \
--header 'Authorization: Your Authorization Token' \
--header 'api-key: Your API Key ID'
```

> Example Response

```json
[
  {
    "id": "bd3335ea-90a4-4958-86a0-5ac800b2f767",
    "action": "BUY",
    "type": "CALL",
    "lifetime": "GTD",
    "strike": "8500",
    "amount": {
      "coin": "BTC",
      "amount": "0.1"
    },
    "unfilled": {
      "coin": "BTC",
      "amount": "0.1"
    },
    "premium": {
      "unitPremium": "244.3",
      "tradeUnitPremium": "24.43",
      "totalPremium": "24.43"
    },
    "asset": "BTC",
    "currency": "SP$",
    "createdAt": "2019-09-30T05:54:04.687Z",
    "expiry": "2019-10-11T08:00:00.000Z",
    "status": "BOOKED",
    "locked": {
      "txFee": {
        "coin": "SP$",
        "amount": "0.780946",
        "sp$Equivalent": "0.780946"
      },
      "tradeLock": null,
      "premium": {
        "unitPremium": "244.3",
        "tradeUnitPremium": "24.43",
        "totalPremium": "24.43"
      }
    },
    "matched": {
      "amount": null,
      "payoff": null,
      "tradeLock": null,
      "tradeRelease": null,
      "premium": null
    },
    "contracts": [],
    "orderType": "PREMIUM",
    "impliedVolatility": "0.92686728"
  },
  ...
]

```


### URL Endpoint
`https://api.sparrowsandbox.com/trades/book/own?orderby=expiry&order=asc`

### HEADERS
Parameter |  value
--------- | ------- 
Authorization | Your authorization key
api-key | Your API Key ID

### PARAMS
Parameter |  value
--------- | ------- 
orderby | expiry
order | asc



<!-- END GET - Order Book depth Filter by Action-->


## GET - Display own bidding and processing trade orders

```shell
curl --location --request GET 'https://api.sparrowsandbox.com/trades/book/own?status=open' \
--header 'Authorization: Your Authorization Token' \
--header 'api-key: Your API Key ID'
```

> Example Response

```json
[
  {
    "id": "bd3335ea-90a4-4958-86a0-5ac800b2f767",
    "action": "BUY",
    "type": "CALL",
    "lifetime": "GTD",
    "strike": "8500",
    "amount": {
      "coin": "BTC",
      "amount": "0.1"
    },
    "unfilled": {
      "coin": "BTC",
      "amount": "0.1"
    },
    "premium": {
      "unitPremium": "244.3",
      "tradeUnitPremium": "24.43",
      "totalPremium": "24.43"
    },
    "asset": "BTC",
    "currency": "SP$",
    "createdAt": "2019-09-30T05:54:04.687Z",
    "expiry": "2019-10-11T08:00:00.000Z",
    "status": "BOOKED",
    "locked": {
      "txFee": {
        "coin": "SP$",
        "amount": "0.780946",
        "sp$Equivalent": "0.780946"
      },
      "tradeLock": null,
      "premium": {
        "unitPremium": "244.3",
        "tradeUnitPremium": "24.43",
        "totalPremium": "24.43"
      }
    },
    "matched": {
      "amount": null,
      "payoff": null,
      "tradeLock": null,
      "tradeRelease": null,
      "premium": null
    },
    "contracts": [],
    "orderType": "PREMIUM",
    "impliedVolatility": "0.93049904"
  }
]
```


### URL Endpoint
`https://api.sparrowsandbox.com/trades/book/own?status=open`

### HEADERS
Parameter |  value
--------- | ------- 
Authorization | Your authorization key
api-key | Your API Key ID

### PARAMS
Parameter |  value
--------- | ------- 
status | open



<!-- END GET - Order Book depth Filter by Action-->


## GET - Display own bidding and processing trade orders - custom

```shell
curl --location --request GET 'https://api.sparrowsandbox.com/trades/book/own?status=open&orderby=expiry&order=asc' \
--header 'Authorization: Your Authorization Token' \
--header 'api-key: Your API Key ID
```

> Example Response

```json
[
  {
    "id": "bd3335ea-90a4-4958-86a0-5ac800b2f767",
    "action": "BUY",
    "type": "CALL",
    "lifetime": "GTD",
    "strike": "8500",
    "amount": {
      "coin": "BTC",
      "amount": "0.1"
    },
    "unfilled": {
      "coin": "BTC",
      "amount": "0.1"
    },
    "premium": {
      "unitPremium": "244.3",
      "tradeUnitPremium": "24.43",
      "totalPremium": "24.43"
    },
    "asset": "BTC",
    "currency": "SP$",
    "createdAt": "2019-09-30T05:54:04.687Z",
    "expiry": "2019-10-11T08:00:00.000Z",
    "status": "BOOKED",
    "locked": {
      "txFee": {
        "coin": "SP$",
        "amount": "0.780946",
        "sp$Equivalent": "0.780946"
      },
      "tradeLock": null,
      "premium": {
        "unitPremium": "244.3",
        "tradeUnitPremium": "24.43",
        "totalPremium": "24.43"
      }
    },
    "matched": {
      "amount": null,
      "payoff": null,
      "tradeLock": null,
      "tradeRelease": null,
      "premium": null
    },
    "contracts": [],
    "orderType": "PREMIUM",
    "impliedVolatility": "0.93049904"
  }
]
```


### URL Endpoint
`https://api.sparrowsandbox.com/trades/book/own?status=open&orderby=expiry&order=asc`

### HEADERS
Parameter |  value
--------- | ------- 
Authorization | Your authorization key
api-key | Your API Key ID

### PARAMS
Parameter |  value
--------- | ------- 
status | open
orderby | expiry
order | asc



<!-- END GET - Order Book depth Filter by Action-->


## GET - Display own canceled & expired trade orders 

```shell
curl --location --request GET 'https://api.sparrowsandbox.com/trades/book/own?status=closed' \
--header 'Authorization: Your Authorization Token' \
--header 'api-key: Your API Key ID'
```

> Example Response

```json
[
  {
    "id": "73148dac-ebb7-4c65-85a2-cb37e2e88679",
    "action": "SELL",
    "type": "PUT",
    "lifetime": "GTC",
    "strike": "8000",
    "amount": {
      "coin": "BTC",
      "amount": "0.1"
    },
    "unfilled": {
      "coin": "BTC",
      "amount": "0.1"
    },
    "premium": {
      "unitPremium": "365.24",
      "tradeUnitPremium": "36.524",
      "totalPremium": "36.524"
    },
    "asset": "BTC",
    "currency": "SP$",
    "createdAt": "2019-09-25T07:27:28.936Z",
    "expiry": "2019-10-04T08:00:00.000Z",
    "status": "CANCELED",
    "locked": {
      "txFee": null,
      "tradeLock": null,
      "premium": null
    },
    "matched": {
      "amount": null,
      "payoff": null,
      "tradeLock": null,
      "tradeRelease": null,
      "premium": null
    },
    "contracts": [],
    "orderType": "PREMIUM",
    "impliedVolatility": "1.078306"
  },
  ...
]
```


### URL Endpoint
`https://api.sparrowsandbox.com/trades/book/own?status=closed`

### HEADERS
Parameter |  value
--------- | ------- 
Authorization | Your authorization key
api-key | Your API Key ID

### PARAMS
Parameter |  value
--------- | ------- 
status | closed



<!-- END GET - Order Book depth Filter by Action-->


## GET - Display own canceled & expired trade orders - custom 

```shell
curl --location --request GET 'https://api.sparrowsandbox.com/trades/book/own?status=closed&orderby=expiry&order=asc' \
--header 'Authorization: Your Authorization Token' \
--header 'api-key: Your API Key ID'
```

> Example Response

```json
[
  {
    "id": "49c95251-6182-436e-9631-d39bf93ae225",
    "action": "BUY",
    "type": "CALL",
    "lifetime": "GTC",
    "strike": "11000",
    "amount": {
      "coin": "BTC",
      "amount": "0.1"
    },
    "unfilled": {
      "coin": "BTC",
      "amount": "0.1"
    },
    "premium": {
      "unitPremium": "46.72",
      "tradeUnitPremium": "4.672",
      "totalPremium": "4.672"
    },
    "asset": "BTC",
    "currency": "SP$",
    "createdAt": "2019-09-24T16:19:48.520Z",
    "expiry": "2019-10-04T08:00:00.000Z",
    "status": "CANCELED",
    "locked": {
      "txFee": null,
      "tradeLock": null,
      "premium": null
    },
    "matched": {
      "amount": null,
      "payoff": null,
      "tradeLock": null,
      "tradeRelease": null,
      "premium": null
    },
    "contracts": [],
    "orderType": "PREMIUM",
    "impliedVolatility": "0.66075075"
  },
  ...
]
```


### URL Endpoint
`https://api.sparrowsandbox.com/trades/book/own?status=closed&orderby=expiry&order=asc`

### HEADERS
Parameter |  value
--------- | ------- 
Authorization | Your authorization key
api-key | Your API Key ID

### PARAMS
Parameter |  value
--------- | ------- 
status | closed
orderby | expiry
order | asc



<!-- END GET - Order Book depth Filter by Action-->
