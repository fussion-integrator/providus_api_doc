1. Payment

# Providus Fund Transfer

Get the status of a transaction .

#### Test Base URL

https://api-staging.providusbank.com

#### Production Base URL

https://api.providusbank.com

#### HTTP Request

POST /ProvidusFundTransfer

## Providus Fund Transfer.

`POST``https://api-staging.providusbank.com/v1/NIPFundTransfer`Transfer fund using providus.

#### Headers

Accept*

application/json

Content-Type*

application/json

#### Request Body

transactionAmount*

String

currencyCode*

String

beneficiaryAccountName*

String

narration

String

sourceAccountName

String

beneficiaryAccountNumber*

String

beneficiaryBank*

String

transactionReference*

String

userName*

String

password*

String

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "transactionReference": "20191119143854",
    "sessionId": "999037230913163757005000082268", 
    "responseMessage": " Approved or completed successfully", 
    "responseCode": "00"
}
inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap whitespace-pre-wrap
curl --location 'https://api-staging.providusbank.com/ProvidusFundTransfer' \
--header 'Accept: application/json' \
--header 'Content-Type: application/json' \
--data '{ "creditAccount":"5900174721", "debitAccount":"1700313889",
"transactionAmount": "2000.45", "currencyCode":"NGN", "narration":"Testing", "transactionReference":"20191119143501", "userName":"test",
"password":"test" }'
inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "amount":"100.0", 
    "transactionReference":"2345677777", 
    "currency":"NGN", 
    "responseMessage":"OPERATION SUCCESSFUL", 
    "responseCode":"00"
}


> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "amount":"100.0", 
    "transactionReference":"2345677777", 
    "currency":"NGN", 
    "responseMessage":"OPERATION SUCCESSFUL", 
    "responseCode":"00"
}


> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "amount":"100.0", 
    "transactionReference":"2345677777", 
    "currency":"NGN", 
    "responseMessage":"OPERATION SUCCESSFUL", 
    "responseCode":"00"
}


> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "amount":"100.0", 
    "transactionReference":"2345677777", 
    "currency":"NGN", 
    "responseMessage":"OPERATION SUCCESSFUL", 
    "responseCode":"00"
}


> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "amount":"100.0", 
    "transactionReference":"2345677777", 
    "currency":"NGN", 
    "responseMessage":"OPERATION SUCCESSFUL", 
    "responseCode":"00"
}


> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "amount":"100.0", 
    "transactionReference":"2345677777", 
    "currency":"NGN", 
    "responseMessage":"OPERATION SUCCESSFUL", 
    "responseCode":"00"
}
```

Last updated 1 year ago