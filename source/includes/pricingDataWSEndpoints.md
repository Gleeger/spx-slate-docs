# Pricing Data (Websocket)

The base endpoint is: 

Production : `https://pricing.sparrowexchange.com/v1/ws` 

Sandbox : `https://pricing.sparrowsandbox.com/v1/ws`

All symbols for streams are uppercase

Please find sample scripts below with socket.io client library

> Sample Scripts with socket.io client library

```html
<!DOCTYPE HTML>
<html>
<head>
    <script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
    <script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/socket.io/2.2.0/socket.io.js"></script>
    <script type="text/javascript" charset="utf-8">
        $(document).ready(function() {
            var host = "https://pricing.sparrowexchange.com";

            // tick price and price change
            var ws_tick = host+"/v1/ws/tick"  
            var tick_socket = io.connect(ws_tick,{transports:["websocket"]}); 
            tick_socket.on('tick_change',function(message1) {
                        console.log(message1);
                    });

            // all OHLC data with identifier 'interval': 1T 5T 15T 30T 1H 4H 1D
            // ohlc_BTC-SP$ received messages for BTC. 
            // ohlc_ETH-SP$ eceived messages for ETH
            tick_socket.on('ohlc_BTC-SP$',function(message1) {
                         console.log('ohlc')
                         console.log(message1);
            //             // filter message by interval for further prcocess
                     });

             tick_socket.on('settlement_datetime',function(message1) {
                         console.log('settlement_datetime')
                         console.log(message1);
                     });

             tick_socket.emit('get_server_time',function(message1) {
                             console.log("get_server_time");
                             console.log(message1)
                         });
            
            ohlc_hist_req = {"symbol":"BTC-SP$","candle_no":100,"period":"1D","base_timestamp":1584682466823}
             tick_socket.emit('load_ohlc_hist',ohlc_hist_req,function(message1) {
                             console.log("load_ohlc_hist");
                             console.log(message1)
                         });

            // Get options premium  
            var ws_option = host+"/v1/ws/premium"  
            var option_socket = io.connect(ws_option,{transports:["websocket"]}); 
            var strike = 10000
            req_json = {"symbol": "BTC-SP$", "strike":strike,"expiry_date": "01/08/2020", "quantity": 2, "action": "BUY", "type": "CALL"};
            option_socket.emit('get_premium', req_json,function(message1) {
                             console.log("premium_update");
                             console.log(message1)
                         });
        });
    </script>
</head>
<body>
</body>
</html>
```



## Options Pricing


### get_premium

Channel url : `/premium`

Events : `get_premium`

Update frequency: when emit get_premium event

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

### settlement_datetime

Channel url : `/premium`

Events : `settlement_datetime`

Socket pushes all available settlement date and time to clients

Update frequency: once a week after weekly settlement


### get_next_settlement

Channel url : `/premium`

Events : `get_next_settlement`

Socket pushes how long it is from now to next settlement 

Update frequency: when emit get_next_settlement event



<!-- END -->

## Spot Pricing

### tick_change

Channel url : `/tick`

Events : `tick_change`

Socket pushes tick price updates to clients

### OHLC_withSymbol

Channel url : `/tick`

Events: `ohlc_<symbol>` following by symbol. Eg. `ohlc_BTC-SP$`

Socket pushes Kline/Candlestick ohlc updates to clients

Update frequency: push updates every 3 seconds

Supported intervals: 1T, 5T, 15T, 30T, 1H, 4H, 1D

> Example Request

```json
{
    "symbol" : "BTC-SP$",
    "candle_no" : 100,
    "period" : "1D",
    "base_timestamp":1584682466823
}
```

### get_server_time

Channel url : `/tick`

Socket pushes server time to clients

Update frequency: when emit get_server_time event