1. Payment

# Get Providus Transaction Status

Get the status of a transaction .

#### Test Base URL

https://api-staging.providusbank.com

#### Production Base URL

https://api.providusbank.com

#### HTTP Request

POST  /payment/status

## NIP Bank.

`POST``https://api-staging.providusbank.com/v1/account/NIP/banks`Get Providus transactions by status.

#### Request Body

userName

String

Username of account owner

password

String

Password of account owner

transactionReference

String

Reference to the transaction

### Sample Implementation

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap whitespace-pre-wrap
curl -x GET "https://api-staging.providusbank.com/payment/status?transactionReference=prov9988zzjzj11"
  -H "Authorization: {{Authentication token}}"
  -H "userName: userName"
  -H "password: password"
inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "amount":"100.0",
    "creditAccount":"1700263070",
    "debitAccount":"5900085856", "transactionReference":"2345677777", "transactionDateTime":"2020-05-04 14:12:11.0", "currency":"NGN", "responseMessage":
    "OPERATION SUCCESSFUL",
    "responseCode":"00"
}


> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "amount":"100.0",
    "creditAccount":"1700263070",
    "debitAccount":"5900085856", "transactionReference":"2345677777", "transactionDateTime":"2020-05-04 14:12:11.0", "currency":"NGN", "responseMessage":
    "OPERATION SUCCESSFUL",
    "responseCode":"00"
}


> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "amount":"100.0",
    "creditAccount":"1700263070",
    "debitAccount":"5900085856", "transactionReference":"2345677777", "transactionDateTime":"2020-05-04 14:12:11.0", "currency":"NGN", "responseMessage":
    "OPERATION SUCCESSFUL",
    "responseCode":"00"
}


> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "amount":"100.0",
    "creditAccount":"1700263070",
    "debitAccount":"5900085856", "transactionReference":"2345677777", "transactionDateTime":"2020-05-04 14:12:11.0", "currency":"NGN", "responseMessage":
    "OPERATION SUCCESSFUL",
    "responseCode":"00"
}


> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "amount":"100.0",
    "creditAccount":"1700263070",
    "debitAccount":"5900085856", "transactionReference":"2345677777", "transactionDateTime":"2020-05-04 14:12:11.0", "currency":"NGN", "responseMessage":
    "OPERATION SUCCESSFUL",
    "responseCode":"00"
}


> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "amount":"100.0",
    "creditAccount":"1700263070",
    "debitAccount":"5900085856", "transactionReference":"2345677777", "transactionDateTime":"2020-05-04 14:12:11.0", "currency":"NGN", "responseMessage":
    "OPERATION SUCCESSFUL",
    "responseCode":"00"
}
```

Last updated 1 year ago