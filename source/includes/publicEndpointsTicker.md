# Public Endpoints - Ticker

## GET - Check system heartbeat

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
`https://pricing.sparrowsandbox.com/v1/heartbeat`

Return system status


<!-- END -->

## GET - Check system timestamp

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
`https://pricing.sparrowsandbox.com/v1/time`

Return the current timestamp in millseconds on server



<!-- END -->

## GET -  List of symbols

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
`https://pricing.sparrowsandbox.com/v1/tick/:symbol`

Retrieves available trading symbols. This method can be used to see which symbols are available for trading.

<!-- END -->

## GET -  Price range within last 24 hours

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
`https://pricing.sparrowsandbox.com/v1/tick/price_range`

Return ticker price and change comparing to price at 24 hour ago by number and percentage

