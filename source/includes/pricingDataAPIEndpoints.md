# Pricing Data (API)

|Environment| URL
|:----------- | :------- 
|Sandbox| https://pricing.sparrowsandbox.com/v1/
|Production| https://pricing.sparrowexchange.com/v1/

## Ticker - Check system heartbeat

```shell
curl --location --request GET 'https://pricing.sparrowsandbox.com/v1/heartbeat'
```
> Example Response

```json
{
  "message": {
    "connection": true
  },
  "status": "success"
}
```

### URL Endpoint
`GET https://pricing.sparrowsandbox.com/v1/heartbeat`

Return system status


<!-- END -->

## Ticker - Check system timestamp

```shell
curl --location --request GET 'https://pricing.sparrowsandbox.com/v1/time'
```
> Example Response

```json
{
  "message": {
    "serverTime": 1569549768803
  },
  "status": "success"
}
```

### URL Endpoint
`GET https://pricing.sparrowsandbox.com/v1/time`

Return the current timestamp in millseconds on server



<!-- END -->

## Ticker - List of symbols

```shell
curl --location --request GET 'https://pricing.sparrowsandbox.com/v1/symbols'
```
> Example Response

```json
{
  "result": {
    "symbols": [
      "BTC-SP$",
      "ETH-SP$"
    ]
  },
  "status": "success"
}
```

### URL Endpoint
`GET https://pricing.sparrowsandbox.com/v1/tick/:symbol`

Retrieves available trading symbols. This method can be used to see which symbols are available for trading.

<!-- END -->

## Ticker - Price range within last 24 hours

```shell
curl --location --request GET 'https://pricing.sparrowsandbox.com/v1/tick/price_range'
```
> Example Response

```json
{
  "result": [
    {
      "high": 8462.76,
      "low": 7731.83,
      "symbol": "BTC-SP$"
    },
    {
      "high": 170.98,
      "low": 152.37,
      "symbol": "ETH-SP$"
    }
  ],
  "status": "success"
}
```

### URL Endpoint
`GET https://pricing.sparrowsandbox.com/v1/tick/price_range`

Return ticker price and change comparing to price at 24 hour ago by number and percentage

## Options - Last Settlement Price

```shell
curl --location --request GET 'https://pricing.sparrowsandbox.com/v1/settlement'
```
> Example Response

```json
{
  "pricings": {
    "BTC-SP$": 7802.57,
    "ETH-SP$": 166.88
  },
  "settlementTime": "2019-09-30T08:00:00Z",
  "signature": "iQEcBAABAgAGBQJdkwD6AAoJEOhpe7MWsGgSrtcH/2s3n7BZUDzTLSwCz4EDk7c265pzciDJKMpxZSIFQfLTpQ52xTmbt+MSfvWlnrVBXlJWF5zTN7egjDrZCqqLiT6EXOg+xGdlJY51exoi9cJoI0VJatWA5sjANLje3QCl8xbpXWluwVeZqw159NM42U0Z01uH94DcidzkxXr4JL5WCmVbVN/RU9TmrZXS7F7FQ+IblMPEPYRCwsOYbAts4+FJ5B/Fxk3zXNOLEBxQrNatrSbTpxY/JxucXP/bxkT4s3RqOV1p2S0DSm0x9cA3gg5RpmWwFaX109lo5y9BEuzn0/zzCZ/tRI9lSH/gZr9MjcM84kqOjHOAhq0KiarOMFE==5wq6"
}
```

### URL Endpoint
`GET https://pricing.sparrowsandbox.com/v1/settlement`

Return last settlement price. It refreshes on fixed time(currently 8AM UTC) on daily basis.

<!-- END -->

## Options - Historical settlement prices

```shell
curl --location --request GET 'https://pricing.sparrowsandbox.com/v1/settlement_hist/:days'
```
> Example Response

```json
[
  {
    "settlement_time": "2019-09-26T08:00:00Z",
    "price": {
      "BTC-USD": 8376.68,
      "ETH-USD": 169.15
    }
  },
  {
    "settlement_time": "2019-09-25T08:00:00Z",
    "price": {
      "BTC-USD": 8357.81,
      "ETH-USD": 164.96
    }
  },
  {
    "settlement_time": "2019-09-24T08:00:00Z",
    "price": {
      "BTC-USD": 9736.85,
      "ETH-USD": 198.74
    }
  },
  {
    "settlement_time": "2019-09-23T08:00:00Z",
    "price": {
      "BTC-USD": 9894.95,
      "ETH-USD": 208.5
    }
  },
  {
    "settlement_time": "2019-09-22T08:00:00Z",
    "price": {
      "BTC-USD": 10001.7,
      "ETH-USD": 212.17
    }
  }
]
```

### URL Endpoint
`GET https://pricing.sparrowsandbox.com/v1/settlement_hist/:days`

Retrieve historical settlement prices up to 31 days

### PARAMS
Parameter |  value
--------- | ------- 
days | 1 (up to 31)

<!-- END -->

## Options - Upcoming settlement dates

```shell
curl --location --request GET 'https://pricing.sparrowsandbox.com/v1/settlement_dates'
```
> Example Response

```json
{
  "result": {
    "settlement_dates": [
      "27/09/2019",
      "04/10/2019",
      "11/10/2019",
      "18/10/2019"
    ],
    "settlement_time": [
      "2019-09-27T08:00",
      "2019-10-04T08:00",
      "2019-10-11T08:00",
      "2019-10-18T08:00"
    ]
  },
  "status": "success"
}
```

### URL Endpoint
`GET https://pricing.sparrowsandbox.com/v1/settlement_dates`

Return upcoming settlement datetime

<!-- END -->

## Options - Options Price

```shell
curl --location --request GET 'https://pricing.sparrowsandbox.com/v1/option/price?symbol=BTC-SP$&strike=8500&expiry_date=11/10/2019&quantity=1.1&action=buy&type=call' \
--header 'Content-Type: application/json'
```
> Example Response

```json
{
  "result": {
    "expiry_date": "11/10/2019",
    "iv": 1.0393,
    "option_price": 505.93,
    "quantity": 1.1,
    "spot": 8018.15,
    "strike": 8500
  },
  "status": "success"
}
```

### URL Endpoint
`GET https://pricing.sparrowsandbox.com/v1/option/price?symbol=:symbol&strike=:strike&expiry_date=:expiry_date&quantity=:quantity&action=:action&type=:type`

Return option price. The strike and quantity should follow step size which vary from time and time.The unit for option price is SP$.iv is implied volatility at which price is calculated.

### HEADERS
Parameter |  value
--------- | ------- 
Content-Type | application/json

### PARAMS
Parameter |  value
--------- | ------- 
symbol | :symbol (symbol for option trading. symbol supported can be retrieved from /symbols)
strike | :strike (strike price)
expiry_date | :expiry_date (option expiry date in DD/MM/YYYY format)
quantity | :quantity (option size)
action | :action (buy or sell)
type | :type (call or put)


<!-- END -->

## Options - Current market iv

```shell
curl --location --request GET 'https://pricing.sparrowsandbox.com/v1/option/iv?symbol=BTC-SP$&strike=8500&expiry_days=4&action=buy&type=call' \
--header 'Content-Type: application/json'
```
> Example Response

```json
{
  "action": "buy",
  "expiry_days": 4,
  "iv": 1.6643,
  "strike": 8500,
  "symbol": "BTC-SP$",
  "type": "call"
}
```

### URL Endpoint
`GET https://pricing.sparrowsandbox.com/v1/option/iv?symbol=:symbol&strike=:strike&expiry_days=:expiry_days&action=:action&type=:type`

Return current implied volatility


### HEADERS
Parameter |  value
--------- | ------- 
Content-Type | application/json

### PARAMS
Parameter |  value
--------- | ------- 
symbol | :symbol (symbol for option trading. symbol supported can be retrieved from /symbols)
strike | :strike (strike price)
expiry_days | :expiry_days (number of days from now to expiry date)
quantity | :quantity (option size)
action | :action (buy or sell)
type | :type (call or put)

