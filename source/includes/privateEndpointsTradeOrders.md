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

```javascript
var myHeaders = new Headers();
myHeaders.append("Content-Type", "application/json");
myHeaders.append("Authorization", "Your Authorization Token");
myHeaders.append("api-key", "Your API Key ID");

var raw = JSON.stringify({"action":"BUY","type":"PUT","lifetime":"GTD","txFeeCoin":"SP$","pair":"BTC-SP$","strike":"7000","amount":"10","tradeUnitPremium":"0.2","expiryDate":"2019-03-01T08:00:00.000Z"});

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
payload = "{\n\t\"action\": \"BUY\",\n\t\"type\": \"PUT\",\n\t\"lifetime\": \"GTD\",\n\t\"txFeeCoin\": \"SP$\",\n\t\"pair\": \"BTC-SP$\",\n\t\"strike\": \"7000\",\n\t\"amount\": \"10\",\n\t\"tradeUnitPremium\": \"0.2\",\n\t\"expiryDate\": \"2019-03-01T08:00:00.000Z\"\n}"
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
request.body = "{\n\t\"action\": \"BUY\",\n\t\"type\": \"PUT\",\n\t\"lifetime\": \"GTD\",\n\t\"txFeeCoin\": \"SP$\",\n\t\"pair\": \"BTC-SP$\",\n\t\"strike\": \"7000\",\n\t\"amount\": \"10\",\n\t\"tradeUnitPremium\": \"0.2\",\n\t\"expiryDate\": \"2019-03-01T08:00:00.000Z\"\n}"

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

  payload := strings.NewReader("{\n	\"action\": \"BUY\",\n	\"type\": \"PUT\",\n	\"lifetime\": \"GTD\",\n	\"txFeeCoin\": \"SP$\",\n	\"pair\": \"BTC-SP$\",\n	\"strike\": \"7000\",\n	\"amount\": \"10\",\n	\"tradeUnitPremium\": \"0.2\",\n	\"expiryDate\": \"2019-03-01T08:00:00.000Z\"\n}")

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

```javascript
var myHeaders = new Headers();
myHeaders.append("Content-Type", "application/json");
myHeaders.append("Authorization", "Your Authorization Token");
myHeaders.append("api-key", "Your API Key ID");

var raw = JSON.stringify({"action":"BUY","type":"PUT","lifetime":"GTD","txFeeCoin":"SP$","pair":"BTC-SP$","strike":"7000","amount":"0.8","unitPremium":"1","expiryDate":"2019-03-10T08:00:00.000Z","skipBidding":true});

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
payload = "{\n\t\"action\": \"BUY\",\n\t\"type\": \"PUT\",\n\t\"lifetime\": \"GTD\",\n\t\"txFeeCoin\": \"SP$\",\n\t\"pair\": \"BTC-SP$\",\n\t\"strike\": \"7000\",\n\t\"amount\": \"0.8\",\n\t\"unitPremium\": \"1\",\n\t\"expiryDate\": \"2019-03-10T08:00:00.000Z\",\n\t\"skipBidding\": true\n}"
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
request.body = "{\n\t\"action\": \"BUY\",\n\t\"type\": \"PUT\",\n\t\"lifetime\": \"GTD\",\n\t\"txFeeCoin\": \"SP$\",\n\t\"pair\": \"BTC-SP$\",\n\t\"strike\": \"7000\",\n\t\"amount\": \"0.8\",\n\t\"unitPremium\": \"1\",\n\t\"expiryDate\": \"2019-03-10T08:00:00.000Z\",\n\t\"skipBidding\": true\n}"

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

  payload := strings.NewReader("{\n	\"action\": \"BUY\",\n	\"type\": \"PUT\",\n	\"lifetime\": \"GTD\",\n	\"txFeeCoin\": \"SP$\",\n	\"pair\": \"BTC-SP$\",\n	\"strike\": \"7000\",\n	\"amount\": \"0.8\",\n	\"unitPremium\": \"1\",\n	\"expiryDate\": \"2019-03-10T08:00:00.000Z\",\n	\"skipBidding\": true\n}")

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

```javascript
var myHeaders = new Headers();
myHeaders.append("Content-Type", "application/json");
myHeaders.append("Authorization", "Your Authorization Token");
myHeaders.append("api-key", "Your API Key ID");

var raw = JSON.stringify([{"action":"BUY","type":"PUT","lifetime":"GTD","txFeeCoin":"SP$","pair":"BTC-SP$","strike":"7000","amount":"1","unitPremium":"2","expiryDate":"2019-10-04T08:00:00.000Z"},{"action":"SELL","type":"PUT","lifetime":"GTD","txFeeCoin":"SPO","pair":"BTC-SP$","strike":"6000","amount":"2","unitPremium":"2.5","expiryDate":"2019-12-01T08:00:00.000Z"}]);

var requestOptions = {
  method: 'POST',
  headers: myHeaders,
  body: raw,
  redirect: 'follow'
};

fetch("https://api.sparrowsandbox.com/trades/book/bulkCreate", requestOptions)
  .then(response => response.text())
  .then(result => console.log(result))
  .catch(error => console.log('error', error))
```

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("https://api.sparrowsandbox.com/trades")
payload = "[\n\t{\n\t\t\"action\": \"BUY\",\n\t\t\"type\": \"PUT\",\n\t\t\"lifetime\": \"GTD\",\n\t\t\"txFeeCoin\": \"SP$\",\n\t\t\"pair\": \"BTC-SP$\",\n\t\t\"strike\": \"7000\",\n\t\t\"amount\": \"1\",\n\t\t\"unitPremium\": \"2\",\n\t\t\"expiryDate\": \"2019-10-04T08:00:00.000Z\"\n\t},\n\t{\n\t\t\"action\": \"SELL\",\n\t\t\"type\": \"PUT\",\n\t\t\"lifetime\": \"GTD\",\n\t\t\"txFeeCoin\": \"SPO\",\n\t\t\"pair\": \"BTC-SP$\",\n\t\t\"strike\": \"6000\",\n\t\t\"amount\": \"2\",\n\t\t\"unitPremium\": \"2.5\",\n\t\t\"expiryDate\": \"2019-12-01T08:00:00.000Z\"\n\t}\n]"
headers = {
  'Content-Type': 'application/json',
  'Authorization': 'Your Authorization Token',
  'api-key': 'Your API Key ID'
}
conn.request("POST", "/book/bulkCreate", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

```ruby
require "uri"
require "net/http"

url = URI("https://api.sparrowsandbox.com/trades/book/bulkCreate")

https = Net::HTTP.new(url.host, url.port);
https.use_ssl = true

request = Net::HTTP::Post.new(url)
request["Content-Type"] = "application/json"
request["Authorization"] = "Your Authorization Token"
request["api-key"] = "Your API Key ID"
request.body = "[\n\t{\n\t\t\"action\": \"BUY\",\n\t\t\"type\": \"PUT\",\n\t\t\"lifetime\": \"GTD\",\n\t\t\"txFeeCoin\": \"SP$\",\n\t\t\"pair\": \"BTC-SP$\",\n\t\t\"strike\": \"7000\",\n\t\t\"amount\": \"1\",\n\t\t\"unitPremium\": \"2\",\n\t\t\"expiryDate\": \"2019-10-04T08:00:00.000Z\"\n\t},\n\t{\n\t\t\"action\": \"SELL\",\n\t\t\"type\": \"PUT\",\n\t\t\"lifetime\": \"GTD\",\n\t\t\"txFeeCoin\": \"SPO\",\n\t\t\"pair\": \"BTC-SP$\",\n\t\t\"strike\": \"6000\",\n\t\t\"amount\": \"2\",\n\t\t\"unitPremium\": \"2.5\",\n\t\t\"expiryDate\": \"2019-12-01T08:00:00.000Z\"\n\t}\n]"

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

  url := "https://api.sparrowsandbox.com/trades/book/bulkCreate"
  method := "POST"

  payload := strings.NewReader("[\n	{\n		\"action\": \"BUY\",\n		\"type\": \"PUT\",\n		\"lifetime\": \"GTD\",\n		\"txFeeCoin\": \"SP$\",\n		\"pair\": \"BTC-SP$\",\n		\"strike\": \"7000\",\n		\"amount\": \"1\",\n		\"unitPremium\": \"2\",\n		\"expiryDate\": \"2019-10-04T08:00:00.000Z\"\n	},\n	{\n		\"action\": \"SELL\",\n		\"type\": \"PUT\",\n		\"lifetime\": \"GTD\",\n		\"txFeeCoin\": \"SPO\",\n		\"pair\": \"BTC-SP$\",\n		\"strike\": \"6000\",\n		\"amount\": \"2\",\n		\"unitPremium\": \"2.5\",\n		\"expiryDate\": \"2019-12-01T08:00:00.000Z\"\n	}\n]")

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

```javascript
var myHeaders = new Headers();

var requestOptions = {
  method: 'GET',
  headers: myHeaders,
  redirect: 'follow'
};

fetch("https://api.sparrowsandbox.com/trades/book", requestOptions)
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

}
conn.request("GET", "/trades/book", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

```go
package main

import (
  "fmt"
  "net/http"
  "io/ioutil"
)

func main() {

  url := "https://api.sparrowsandbox.com/trades/book"
  method := "GET"

  client := &http.Client {
  }
  req, err := http.NewRequest(method, url, nil)

  if err != nil {
    fmt.Println(err)
  }
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

```javascript
var myHeaders = new Headers();

var requestOptions = {
  method: 'GET',
  headers: myHeaders,
  redirect: 'follow'
};

fetch("https://api.sparrowsandbox.com/trades/book", requestOptions)
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

}
conn.request("GET", "/trades/book", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

```go
package main

import (
  "fmt"
  "net/http"
  "io/ioutil"
)

func main() {

  url := "https://api.sparrowsandbox.com/trades/book"
  method := "GET"

  client := &http.Client {
  }
  req, err := http.NewRequest(method, url, nil)

  if err != nil {
    fmt.Println(err)
  }
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

```javascript
var requestOptions = {
  method: 'GET',
  redirect: 'follow'
};

fetch("https://api.sparrowsandbox.com/trades/book/BTC-SP$", requestOptions)
  .then(response => response.text())
  .then(result => console.log(result))
  .catch(error => console.log('error', error));
```

```ruby
require "uri"
require "net/http"

url = URI("https://api.sparrowsandbox.com/trades/book/BTC-SP$")

https = Net::HTTP.new(url.host, url.port);
https.use_ssl = true

request = Net::HTTP::Get.new(url)

response = https.request(request)
puts response.read_body

```

```python
import http.client
import mimetypes
conn = http.client.HTTPSConnection("https://api.sparrowsandbox.com/trades")
payload = ''
headers = {}
conn.request("GET", "/book/BTC-SP$", payload, headers)
res = conn.getresponse()
data = res.read()
print(data.decode("utf-8"))
```

```go
package main

import (
  "fmt"
  "net/http"
  "io/ioutil"
)

func main() {

  url := "https://api.sparrowsandbox.com/trades/book/BTC-SP$"
  method := "GET"

  client := &http.Client {
  }
  req, err := http.NewRequest(method, url, nil)

  if err != nil {
    fmt.Println(err)
  }
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