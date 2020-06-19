---
title: Sparrow API Documentation

language_tabs: # must be one of https://git.io/vQNgJ
  - shell

toc_footers:
  - <a href='https://sparrowexchange.com/'>Sparrow</a>

includes:
  - privateEndpoints
  - privateEndpointsWebsocket
  - publicEndpoints
  - publicEndpointsWebsocket
  - questionsOrComments

search: true
---
# Welcome to Sparrow's API. 

This documentation will list all available API endpoints for Sparrow users to interact with the platform.

#  Sparrow Environments

Sparrow have two API environments, Sparrow Sandbox and Sparrow Production. Sparrow Sandbox can be used for users to test their API before deploying the application to Sparrow Production. 

|Environment| URL
|:----------- | :------- 
|Sandbox| https://sparrowsandbox.com/ 
|Production| https://sparrowexchange.com/ 


**Note:**

- Each platform will have separate API keys for each environment.
- Data created or modified in each environment will not affect the other. 
- Please **DO NOT** deposit any digital asset to Sparrow Sandbox environment. You may contact support@sparrowexchange.com if you need testing fund in your Sandbox account. 


# API Keys

|Environment| URL
|:----------- | :------- 
|Sandbox| https://api.sparrowsandbox.com/ 
|Production| https://api.sparrowexchange.com/ 

Before you start using Sparrow API, you will need to enable your API access by creating {{api_key_id}} and download your API RSA Private key in PEM format (api.pem). 

In order to do so, you will need to login with your account and go to **API Management** > **New API** to submit your API Key request with the necessary privileges. 

![Sparrow API Key Creations](https://spx-publicassets.s3-ap-southeast-1.amazonaws.com/img/1Keycreation.png)

Once your API Key request has been submitted, you will receive an API Key Request confirmation email for you to confirm and download the API RSA Private key in PEM format (api.pem). 

The private key can be opened by any text editor with the content looks like below: 
```
-----BEGIN RSA PRIVATE KEY-----
MIIEogIBAAKCAQEAv1oaYMFaXX/FRrlNyDloizH/1W7cKJAGac9G0PCEZsFgcGBi
... ... 
ZwPHzaUUtebC6ge9rboRaRsS+wFYVU6OkdEVJIDasm4XMf+etS8=
-----END RSA PRIVATE KEY-----
```
Think of your API RSA Private key like a password:

- Store it **securely**
- **Don't** share it with anyone
- **Don't** put it in any code that is publicly accessible 

You will also need {{api_key_id}}, which can be found in **API Management** > **API Key ID**. This will also be used to generate and sign access token for your application. 

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

# Wallet 
... Account Balance Endpoint will be here ...
## Account Balance Endpoint Will be here

# Options Trade
... Trade Orders Endpoint Will be here ...

## Public WebSocket

...

## Private WebSocket
|Environment| URL
|:----------- | :------- 
|Sandbox| https://ws.sparrowsandbox.com/ 
|Production| https://ws.sparrowexchange.com/ 


# Conversions

# Pricing Data(API)
|Environment| URL
|:----------- | :------- 
|Sandbox| https://pricing.sparrowsandbox.com/v1/
|Production| https://pricing.sparrowexchange.com/v1/

## More api will be here


# Pricing Data(WebSocket)
|Environment| URL
|:----------- | :------- 
|Sandbox| https://api.sparrowsandbox.com/v1/ws
|Production| https://api.sparrowexchange.com/v1/ws

## More api will be here
