# Authentication 

All requests to Sparrow Private API and WebSocket endpoints are required to be signed with an API Key and JWT token. 

This section will provide you how to use the API Key ID and RSA Private Key (api.pem) to generate and sign JWT token for your application. 

To generate a signed JWT token, you will need:

1. Your **User ID** (can be found under your Sparrow Dashboard **Account** tab)
2. Your **API Key ID** (can be found under your Sparrow Dashboard **API Management** tab)
3. Your **RSA Private Key** downloaded (api.pem)

You can sign and generate the token with any programming languages such as `Python` and `Go`. Below are some samples for your reference. 

# Making Your First Call


Test that you have the headers setup by making a `GET` request to `"wallets/balance"` with the above API Request Headers obtained from the Authentication session. You should get a `HTTP 200 OK` response if your keys are correct.


**NOTE:** 

You'll need to have the API Request Headers with Authorization token in all API requests to Sparrow Private API and WebSocket endpoints, except Public API endpoints where Authorization token is not required. 
