<!-- This docs has been moved to optionsTradeEndpoints -->
# Private Endpoints - Websocket
When connected to the websocket, it will receives two types of messages: (1)all new orders created via sparrow options web platform (2)new contracts when your order matched

## HEAD - Streaming URL
```shell
curl --location --head 'https://ws.sparrowsandbox.com/stream?api-key=Your%20API%20Key%20ID&authorization=Your%20Authorization%20Token'
```

This is the URL of websocket to connect to. stream?api-key={{apiKeyId}}&authorization={{token}} api-key is user's api key authorization is the token signed with private key See API key section for details on how to generate authorization

### URL Endpoint
`https://ws.sparrowsandbox.com/stream?api-key=Your API Key ID&authorization=Your Authorization Token`

### HEADERS
Parameter | Default 
--------- | ------- 
Content-Type | application/json
Authorization | Your Authorization Token

<!-- END  POST - Create new trade order with unitPremium -->