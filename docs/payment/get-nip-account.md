1. Payment

# Get NIP Account

## Request Body

```json
{
  "userName": "\"userName_value\"",
  "password": "\"password_value\""
}
```

### Parameters

| Parameter | Type | Description |
|-----------|------|--------------|
| userName | string | Username of account owner |
| password | string | Password of account owner |

Get the details of an NIP account.

#### Test Base URL

https://api-staging.providusbank.com

#### Production Base URL

https://api.providusbank.com

#### HTTP Request

POST /GetNIPAccount

## NIP Account.

`POST``https://api-staging.providusbank.com/v1/GetNIPAccount`Get NIP Account.

#### Request Body

accountNumber*

string

account number for the account

beneficiaryBank*

string

code of the bank





```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "bankCode":"57",
    "accountName":"NNAJI, JOSHUA & VIVIAN",
    "transactionReference":"",
    "bvn":"",
    "responseMessage":" Approved or completed successfully",
    "accountNumber":"3041004406",
    "responseCode":"00"
}
inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap whitespace-pre-wrap
curl -x POST "https://api-staging.providusbank.com/account/NIP?accountNumber=3041004406&beneficiaryBank=57"
  -H "Authorization: {{Authentication token}}"
  -H "Username: Username"
  -H "password: Password"
inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "bankCode":"57",
    "accountName":"NNAJI, JOSHUA & VIVIAN",
    "transactionReference":"",
    "bvn":"",
    "responseMessage":" Approved or completed successfully",
    "accountNumber":"3041004406",
    "responseCode":"00"
}


> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "bankCode":"57",
    "accountName":"NNAJI, JOSHUA & VIVIAN",
    "transactionReference":"",
    "bvn":"",
    "responseMessage":" Approved or completed successfully",
    "accountNumber":"3041004406",
    "responseCode":"00"
}


> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "bankCode":"57",
    "accountName":"NNAJI, JOSHUA & VIVIAN",
    "transactionReference":"",
    "bvn":"",
    "responseMessage":" Approved or completed successfully",
    "accountNumber":"3041004406",
    "responseCode":"00"
}


> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "bankCode":"57",
    "accountName":"NNAJI, JOSHUA & VIVIAN",
    "transactionReference":"",
    "bvn":"",
    "responseMessage":" Approved or completed successfully",
    "accountNumber":"3041004406",
    "responseCode":"00"
}


> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "bankCode":"57",
    "accountName":"NNAJI, JOSHUA & VIVIAN",
    "transactionReference":"",
    "bvn":"",
    "responseMessage":" Approved or completed successfully",
    "accountNumber":"3041004406",
    "responseCode":"00"
}


> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "bankCode":"57",
    "accountName":"NNAJI, JOSHUA & VIVIAN",
    "transactionReference":"",
    "bvn":"",
    "responseMessage":" Approved or completed successfully",
    "accountNumber":"3041004406",
    "responseCode":"00"
}
```

Last updated 1 month ago