# Public Endpoints - Websocket

The base endpoint is: 

Production : `https://pricing.sparrowexchange.com/v1/ws` 

Sandbox : `https://pricing.sparrowsandbox.com/v1/ws`

## Options Trading - get_premium

Channel url : `/premium`

Calculate premium for options with specific symbol, strike, expiry date, quantity, buy/sell and call/put

> Example Request

```json
{
   "symbol":"BTC-SP$",
   "strike":10000,
   "expiry_date":"06/03/2020",
   "quantity":2,
   "action":"BUY",
   "type":"CALL"
}
```

<!-- END -->

## Options Trading - list_quick_pick

Channel url : `/premium`

For specific symbol and settlement date, list down a few choices of options for which strike, settlement price,profit return are fixed

> Example Request

```json
{   
    "symbol":"BTC-SP$",
    "expiry_date":"03/04/2020"
}
```

## Options Trading - get_next_settlement

Channel url : `/premium`

Return how long it is from now to next weekly settlement and next daily settlemen

> Example Request

```json
nil
```

<!-- END -->