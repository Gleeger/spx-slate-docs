# Private Endpoints - Account Balance

## GET - Wallet Balance
```shell
curl --location --request GET 'https://api.sparrowsandbox.com/wallets/balance' \
--header 'Authorization: Your Authorization Token' \
--header 'api-key: Your API Key ID' \
--header 'Content-Type: application/json'
```

```javascript
var myHeaders = new Headers();
myHeaders.append("Authorization", "Your Authorization Token");
myHeaders.append("api-key", "Your API Key ID");
myHeaders.append("Content-Type", "application/json");

var requestOptions = {
  method: 'GET',
  headers: myHeaders,
  redirect: 'follow'
};

fetch("https://api.sparrowsandbox.com/wallets/balance", requestOptions)
  .then(response => response.text())
  .then(result => console.log(result))
  .catch(error => console.log('error', error));
```

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("api.sparrowsandbox.com")
payload = ''
headers = {
  'Authorization': 'Your Authorization Token',
  'api-key': 'Your API Key ID',
  'Content-Type': 'application/json'
}
conn.request("GET", "/wallets/balance", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

```ruby
require "uri"
require "net/http"

url = URI("https://api.sparrowsandbox.com/wallets/balance")

https = Net::HTTP.new(url.host, url.port);
https.use_ssl = true

request = Net::HTTP::Get.new(url)
request["Authorization"] = "Your Authorization Token"
request["api-key"] = "Your API Key ID"
request["Content-Type"] = "application/json"

response = https.request(request)
puts response.read_body
```

```go
package main

import (
  "fmt"
  "net/http"
  "io/ioutil"
)

func main() {

  url := "https://api.sparrowsandbox.com/wallets/balance"
  method := "GET"

  client := &http.Client {
  }
  req, err := http.NewRequest(method, url, nil)

  if err != nil {
    fmt.Println(err)
  }
  req.Header.Add("Authorization", "Your Authorization Token")
  req.Header.Add("api-key", "Your API Key ID")
  req.Header.Add("Content-Type", "application/json")

  res, err := client.Do(req)
  defer res.Body.Close()
  body, err := ioutil.ReadAll(res.Body)

  fmt.Println(string(body))
}
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
`https://api.sparrowsandbox.com/wallets/balance`

### HEADERS
Parameter | Default 
--------- | ------- 
Authorization | Your Authorization Token
api-key | Your API KEY ID
Content-Type | application/json

<!-- END GET - WALLET BALANCE -->
<!-- ------ -->

<!-- START GET - WALLET BALANCE (ONLY OPTIONS TRADING PAIRS) -->
## GET - Wallet Balance (Only Options Trading Pairs)

```shell
curl --location --request GET 'https://api.sparrowsandbox.com/wallets/balance?filter=optionsTrading' \
--header 'Authorization: Your Authorization Token' \
--header 'api-key: Your API Key ID'
```

```javascript
var myHeaders = new Headers();
myHeaders.append("Authorization", "Your Authorization Token");
myHeaders.append("api-key", "Your API Key ID");

var requestOptions = {
  method: 'GET',
  headers: myHeaders,
  redirect: 'follow'
};

fetch("https://api.sparrowsandbox.com/wallets/balance?filter=optionsTrading", requestOptions)
  .then(response => response.text())
  .then(result => console.log(result))
  .catch(error => console.log('error', error));
```

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("https://api.sparrowsandbox.com/wallets")
payload = ''
headers = {
  'Authorization': 'Your Authorization Token',
  'api-key': 'Your API Key ID'
}
conn.request("GET", "/balance?filter=optionsTrading", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

```ruby
require "uri"
require "net/http"

url = URI("https://api.sparrowsandbox.com/wallets/balance?filter=optionsTrading")

https = Net::HTTP.new(url.host, url.port);
https.use_ssl = true

request = Net::HTTP::Get.new(url)
request["Authorization"] = "Your Authorization Token"
request["api-key"] = "Your API Key ID"

response = https.request(request)
puts response.read_body
```

```go
package main

import (
  "fmt"
  "net/http"
  "io/ioutil"
)

func main() {

  url := "https://api.sparrowsandbox.com/wallets/balance?filter=optionsTrading"
  method := "GET"

  client := &http.Client {
  }
  req, err := http.NewRequest(method, url, nil)

  if err != nil {
    fmt.Println(err)
  }
  req.Header.Add("Authorization", "Your Authorization Token")
  req.Header.Add("api-key", "Your API Key ID")

  res, err := client.Do(req)
  defer res.Body.Close()
  body, err := ioutil.ReadAll(res.Body)

  fmt.Println(string(body))
}
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
`https://api.sparrowsandbox.com/wallets/balance?filter=optionsTrading`

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

<!-- START  GET - (Option Pairs) Display Options Trading Pairs -->