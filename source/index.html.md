---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell

# toc_footers:
#   - <a href='#'>Sign Up for a Developer Key</a>
#   - <a href='https://github.com/slatedocs/slate'>Documentation Powered by Slate</a>

includes:
  - privateEndpoints
  - privateEndpointsAccountBalance
  - privateEndpointsTradeOptionsPairs
  - privateEndpointsTradeOrders
  - publicEndpoints

search: true
---
# Welcome to Sparrow's API. 

This documentation will list all available API endpoints for Sparrow users to interact with the platform.

#  Sparrow Environments

Sparrow have two API environments, Sparrow Sandbox and Sparrow Production. Sparrow Sandbox can be used for users to test their API before deploying the application to Sparrow Production. 

|Endpoints URLs| Sandbox Environments 
|:----------- | :------- 
|Platform  | https://sparrowsandbox.com/ 
|Private API | https://api.sparrowsandbox.com/ 
|Public API | https://pricing.sparrowsandbox.com/v1/ 
|WebSocket | https://ws.sparrowsandbox.com/ 


|Endpoints URLs| Production Environments
|:----------- | :------- 
|Platform  | https://sparrowexchange.com/ 
|Private API |  https://api.sparrowexchange.com/
|Public API | https://pricing.sparrowexchange.com/v1/
|WebSocket | https://ws.sparrowexchange.com/

**Note:**

- Each platform will have separate API keys for each environment.
- Data created or modified in each environment will not affect the other. 
- Please **DO NOT** deposit any digital asset to Sparrow Sandbox environment. You may contact support@sparrowexchange.com if you need testing fund in your Sandbox account. 


# API Keys

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

## Python

**1. Step 1: Import dependencies**
```python
import jwt
from datetime import datetime, timedelta
```
**2. Step 2: Initialize the required variables**
```python
userId = Your User ID
apiKeyId = {{api_key_id}}
privateKey = Your RSA Private Key
expSec = Token expiry in seconds (max 5 minutes)
```
**3. Step 3: Sign jwt and generate token**
```python
expiryTime = int((datetime.now() + timedelta(seconds=expSec)).timestamp())
currentTime = int((datetime.now().timestamp()))
tokenPayload = {'userId': userId, 'exp': expiryTime, 'iat': currentTime}
signedJwt = jwt.encode(tokenPayload, privateKey, algorithm='RS256')
signedJwt = signedJwt.decode('UTF-8')
```
The value you obtained from `signedJwt` will be {{auth_token}} for each API request to Sparrow Private API and WebSocket endpoints. Below is a sample of the Authorization token for your reference:
```
eyJhbGciOiJSUzI1NiIsInR5cCI6
... ... 
thjybpTcmmoalGz_9EHG048pCBCA
```

**4. Step 4: Construct Your API Request Headers**
```python
"Content-Type": "application/json",
"Authorization": signedJwt,
"api-key": {{api_key_id}}
```

## Go 

```
**1. Step 1: Import dependencies**
```Go
import {
	"bufio"
	"crypto/rsa"
	"crypto/x509"
	"os"
	jwt "github.com/dgrijalva/jwt-go"
	"encoding/pem"
}
```
**2. Step 2: Read private key from file**
```Go
func readPrivateKey(keyPath string) *rsa.PrivateKey {
	privateKeyFile, err := os.Open(keyPath)
	defer privateKeyFile.Close()
	if err != nil {
		log.Errorln(err)
		panic(err)
	}
	pemfileinfo, _ := privateKeyFile.Stat()
	var size = pemfileinfo.Size()
	pembytes := make([]byte, size)

	buffer := bufio.NewReader(privateKeyFile)
	_, err = buffer.Read(pembytes)

	data, _ := pem.Decode([]byte(pembytes))

	privateKeyImported, err := x509.ParsePKCS1PrivateKey(data.Bytes)

	if err != nil {
		panic(err)
	}

	return privateKeyImported
}
```
**3. Step 3: Initialize the required variables**
```Go
userId = Your User ID
apiKeyId = {{api_key_id}}
privateKey = Your RSA Private Key
expSec = Token expiry in seconds (max 5 minutes)
```
**Step 4: Sign jwt and generate token**
```Go
func newAuth(userID string, privateKey *rsa.PrivateKey, expSec int64) string {
	token := jwt.New(jwt.SigningMethodRS256)
	var payload = jwt.MapClaims{"exp": time.Now().Add(time.Second * time.Duration(expSec)).Unix(),
		"userId": userID, "iat": time.Now().Unix()}
	token.Claims = payload
	tokenString, err := token.SignedString(privateKey)

	if err != nil {
		log.Errorln(err)
		return ""
	}
	return tokenString
}
```
The value you obtained from `tokenString` will be {{auth_token}} for each API request to Sparrow Private API and WebSocket endpoints. Below is a sample of the Authorization token for your reference:
```
eyJhbGciOiJSUzI1NiIsInR5cCI6
... ... 
thjybpTcmmoalGz_9EHG048pCBCA
```

**5. Step 5: Construct Your API Request Headers**
```Go
"Content-Type": "application/json",
"Authorization": tokenString,
"api-key": {{api_key_id}}
```

# Making Your First Call


Test that you have the headers setup by making a `GET` request to `"wallets/balance"` with the above API Request Headers obtained from the Authentication session. You should get a `HTTP 200 OK` response if your keys are correct.


**NOTE:** 

You'll need to have the API Request Headers with Authorization token in all API requests to Sparrow Private API and WebSocket endpoints, except Public API endpoints where Authorization token is not required. 

# Questions/Comments

If you have any questions or comments, please let us know at [support@sparrowexchange.com](mailto:support@sparrowexchange.com).




