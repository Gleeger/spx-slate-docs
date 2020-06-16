---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - ruby
  - python
  - javascript
  - go

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the SPARROW API! 



# API Key setup
API Key Setup

Some endpoints will require an API Key. Please refer to this page regarding API key creation.

Once API key is created, it is recommended to set IP restrictions on the key for security reasons.

Never share your API key/secret key to ANYONE.

`Authorization: xyz`

<aside class="notice">
You must replace <code>xyz</code> with your personal API key.
</aside>


# Private Endpoints
<!-- START GET - WALLET BALANCE -->
## [Account Balance] GET - Wallet Balance
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
## [Account Balance] GET - Wallet Balance (Only Options Trading Pairs)
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
## [TRADE] GET - (Option Pairs) Display Options Trading Pairs
```shell
curl --location --request GET 'https://api.sparrowsandbox.com/trades/pairs' \
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

fetch("https://api.sparrowsandbox.com/trades/pairs", requestOptions)
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
  'api-key': 'Your API Key ID'
}
conn.request("GET", "/trades/pairs", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

```ruby
require "uri"
require "net/http"

url = URI("https://api.sparrowsandbox.com/trades/pairs")

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

  url := "https://api.sparrowsandbox.com/trades/pairs"
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


<!-- START POST - Create new trade order with unitPremium -->
## [TRADE] POST - (Orders) - Create new trade order with unitPremium
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

```javascript
var myHeaders = new Headers();
myHeaders.append("Content-Type", "application/json");
myHeaders.append("Authorization", "Your Authorization Token");
myHeaders.append("api-key", "Your API Key ID");

var raw = JSON.stringify({"action":"BUY","type":"CALL","lifetime":"GTD","txFeeCoin":"SP$","pair":"BTC-SP$","strike":"8000","amount":"1","totalPremium":"200","expiryDate":"2019-10-04T08:00"});

var requestOptions = {
  method: 'POST',
  headers: myHeaders,
  body: raw,
  redirect: 'follow'
};

fetch("https://api.sparrowsandbox.com/trades/book/create", requestOptions)
  .then(response => response.text())
  .then(result => console.log(result))
  .catch(error => console.log('error', error));
```

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("api.sparrowsandbox.com")
payload = "{\n\t\"action\": \"BUY\",\n\t\"type\": \"CALL\",\n\t\"lifetime\": \"GTD\",\n\t\"txFeeCoin\": \"SP$\",\n\t\"pair\": \"BTC-SP$\",\n\t\"strike\": \"8000\",\n\t\"amount\": \"1\",\n\t\"totalPremium\": \"200\",\n\t\"expiryDate\": \"2019-10-04T08:00\"\n}"
headers = {
  'Content-Type': 'application/json',
  'Authorization': 'Your Authorization Token',
  'api-key': 'Your API Key ID'
}
conn.request("POST", "/trades/book/create", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

```ruby
require "uri"
require "net/http"

url = URI("https://api.sparrowsandbox.com/trades/book/create")

https = Net::HTTP.new(url.host, url.port);
https.use_ssl = true

request = Net::HTTP::Post.new(url)
request["Content-Type"] = "application/json"
request["Authorization"] = "Your Authorization Token"
request["api-key"] = "Your API Key ID"
request.body = "{\n\t\"action\": \"BUY\",\n\t\"type\": \"CALL\",\n\t\"lifetime\": \"GTD\",\n\t\"txFeeCoin\": \"SP$\",\n\t\"pair\": \"BTC-SP$\",\n\t\"strike\": \"8000\",\n\t\"amount\": \"1\",\n\t\"totalPremium\": \"200\",\n\t\"expiryDate\": \"2019-10-04T08:00\"\n}"

response = https.request(request)
puts response.read_body
```

```go
package main

import (
  "fmt"
  "strings"
  "net/http"
  "io/ioutil"
)

func main() {

  url := "https://api.sparrowsandbox.com/trades/book/create"
  method := "POST"

  payload := strings.NewReader("{\n	\"action\": \"BUY\",\n	\"type\": \"CALL\",\n	\"lifetime\": \"GTD\",\n	\"txFeeCoin\": \"SP$\",\n	\"pair\": \"BTC-SP$\",\n	\"strike\": \"8000\",\n	\"amount\": \"1\",\n	\"totalPremium\": \"200\",\n	\"expiryDate\": \"2019-10-04T08:00\"\n}")

  client := &http.Client {
  }
  req, err := http.NewRequest(method, url, payload)

  if err != nil {
    fmt.Println(err)
  }
  req.Header.Add("Content-Type", "application/json")
  req.Header.Add("Authorization", "Your Authorization Token")
  req.Header.Add("api-key", "Your API Key ID")

  res, err := client.Do(req)
  defer res.Body.Close()
  body, err := ioutil.ReadAll(res.Body)

  fmt.Println(string(body))
}
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

## [TRADE] POST - (Orders) - Create new trade order with totalPremium
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

```javascript
var myHeaders = new Headers();
myHeaders.append("Content-Type", "application/json");
myHeaders.append("Authorization", "Your Authorization Token");
myHeaders.append("api-key", "Your API Key ID");

var raw = JSON.stringify({"action":"BUY","type":"PUT","lifetime":"GTD","txFeeCoin":"SP$","pair":"BTC-SP$","strike":"7000","amount":"3","totalPremium":"10","expiryDate":"2019-04-20T08:00:00.000Z"});

var requestOptions = {
  method: 'POST',
  headers: myHeaders,
  body: raw,
  redirect: 'follow'
};

fetch("https://api.sparrowsandbox.com/trades/book/create", requestOptions)
  .then(response => response.text())
  .then(result => console.log(result))
  .catch(error => console.log('error', error));
```

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("api.sparrowsandbox.com")
payload = "{\n\t\"action\": \"BUY\",\n\t\"type\": \"PUT\",\n\t\"lifetime\": \"GTD\",\n\t\"txFeeCoin\": \"SP$\",\n\t\"pair\": \"BTC-SP$\",\n\t\"strike\": \"7000\",\n\t\"amount\": \"3\",\n\t\"totalPremium\": \"10\",\n\t\"expiryDate\": \"2019-04-20T08:00:00.000Z\"\n}"
headers = {
  'Content-Type': 'application/json',
  'Authorization': 'Your Authorization Token',
  'api-key': 'Your API Key ID'
}
conn.request("POST", "/trades/book/create", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

```ruby
require "uri"
require "net/http"

url = URI("https://api.sparrowsandbox.com/trades/book/create")

https = Net::HTTP.new(url.host, url.port);
https.use_ssl = true

request = Net::HTTP::Post.new(url)
request["Content-Type"] = "application/json"
request["Authorization"] = "Your Authorization Token"
request["api-key"] = "Your API Key ID"
request.body = "{\n\t\"action\": \"BUY\",\n\t\"type\": \"PUT\",\n\t\"lifetime\": \"GTD\",\n\t\"txFeeCoin\": \"SP$\",\n\t\"pair\": \"BTC-SP$\",\n\t\"strike\": \"7000\",\n\t\"amount\": \"3\",\n\t\"totalPremium\": \"10\",\n\t\"expiryDate\": \"2019-04-20T08:00:00.000Z\"\n}"

response = https.request(request)
puts response.read_body
```

```go
package main

import (
  "fmt"
  "strings"
  "net/http"
  "io/ioutil"
)

func main() {

  url := "https://api.sparrowsandbox.com/trades/book/create"
  method := "POST"

  payload := strings.NewReader("{\n	\"action\": \"BUY\",\n	\"type\": \"PUT\",\n	\"lifetime\": \"GTD\",\n	\"txFeeCoin\": \"SP$\",\n	\"pair\": \"BTC-SP$\",\n	\"strike\": \"7000\",\n	\"amount\": \"3\",\n	\"totalPremium\": \"10\",\n	\"expiryDate\": \"2019-04-20T08:00:00.000Z\"\n}")

  client := &http.Client {
  }
  req, err := http.NewRequest(method, url, payload)

  if err != nil {
    fmt.Println(err)
  }
  req.Header.Add("Content-Type", "application/json")
  req.Header.Add("Authorization", "Your Authorization Token")
  req.Header.Add("api-key", "Your API Key ID")

  res, err := client.Do(req)
  defer res.Body.Close()
  body, err := ioutil.ReadAll(res.Body)

  fmt.Println(string(body))
}
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


# Public Endpoints
<!-- ### Get All Kittens

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get()
```

```shell
curl "http://example.com/api/kittens"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let kittens = api.kittens.get();
```

> The above command returns JSON structured like this:

```json
[
  {
    "id": 1,
    "name": "Fluffums",
    "breed": "calico",
    "fluffiness": 6,
    "cuteness": 7
  },
  {
    "id": 2,
    "name": "Max",
    "breed": "unknown",
    "fluffiness": 5,
    "cuteness": 10
  }
]
```

This endpoint retrieves all kittens.

### HTTP Request

`GET http://example.com/api/kittens`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include kittens that have already been adopted.

<aside class="success">
Remember — a happy kitten is an authenticated kitten!
</aside>

## Get a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.get(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.get(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.get(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific kitten.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to retrieve

## Delete a Specific Kitten

```ruby
require 'kittn'

api = Kittn::APIClient.authorize!('meowmeowmeow')
api.kittens.delete(2)
```

```python
import kittn

api = kittn.authorize('meowmeowmeow')
api.kittens.delete(2)
```

```shell
curl "http://example.com/api/kittens/2"
  -X DELETE
  -H "Authorization: meowmeowmeow"
```

```javascript
const kittn = require('kittn');

let api = kittn.authorize('meowmeowmeow');
let max = api.kittens.delete(2);
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted" : ":("
}
```

This endpoint deletes a specific kitten.

### HTTP Request

`DELETE http://example.com/kittens/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the kitten to delete -->

