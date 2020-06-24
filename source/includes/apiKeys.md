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