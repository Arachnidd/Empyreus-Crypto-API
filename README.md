Actual Source code is private, if you wish to view it or want to discuss about it, please message me. This is hosted and acts like an api

# Empyreus-Crypto-API
This is the documentation for Empyreus Crypto API

All requests are POST requests and ALL requests will have the required body parameters alongside the adsitional parameters.

Each POST Request:
{
    "user": "userName"
    "password": "password"
}


/create${Currency}
No request body
Response body:
{
    "privateKey": "key"
    "address": "address"
    "encryption": "encypted"
}

/balance${Currency}
Body Request: 
{
    "address": "address"
}
Response Body:
{
    "status": true,
    "message": [
       "balance": 0.001,
       "totalSent": 0.001,
       "totalReceived": 0.001
    ]
}

/send${Currency}
Request body:
{
    "pkey": "key",
    "to": "address",
    "amount": 0.001
}
Response body:
{
    "status": true,
    "message": [
        "to": "address",
        "amount": 0.001
        "txid": "transactionId"
    ]
}

**Note:** For sending fee is automatically calculated so you do not have to input the fee each time.

pkey = The currency address authentication (sort of like a key to get into the address). This should not be shared with ANYONE.

user = the username assigned to you by the owner
password = the password assigned to you by the owner

Currency = the currency you are dealing with, currently the only ones are: Bitcoin and Litecoin (both of them full names and a capital letter at the biginning).

**REMINDER:** Each request **MUST** contain the username and password in the body params.
