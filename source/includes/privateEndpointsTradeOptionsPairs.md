# Private Endpoints - Trade Options Pairs

## GET - Display Options Trading Pairs
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