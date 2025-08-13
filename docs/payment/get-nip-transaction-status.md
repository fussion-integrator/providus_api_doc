1. Payment

# Get NIP Transaction Status

Get the status of an NIP transaction.

#### Test Base URL

https://api-staging.providusbank.com

#### Production Base URL

https://api.providusbank.com

#### HTTP Request

POST /GetNIPTransactionStatus

## NIP Transaction Account.

`POST``https://api-staging.providusbank.com/v1/GetNIPTransactionStatus`Get NIP Transaction Account Status.

#### Headers

Accept*

application/json

Content-Type*

application/json

#### Request Body

transactionReference*

String

Reference to the transaction

userName*

String

Username of account owner

password*

String

Password of account owner

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "amount":"100.00",
    "recipientBankCode":"000004",
    "recipientAccountNumber":"1020808489",
    "transactionReference":"prov9988zzjzj11| 000023211018133747005000003198",
    "transactionDateTime":"2021-10-18 13:32:28",
    "currency":"1",
    "responseMessage":" Approved or completed successfully",
    "responseCode":"00"
}
inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap whitespace-pre-wrap
curl -x GET "https://api-staging.providusbank.com/payment/NIP/status?transaction_reference=prov9988zzjzj11"
  -H "Authorization: {{Authentication token}}"
  -H "Username: Username"
  -H "Password: Password"
inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "amount":"100.00",
    "recipientBankCode":"000004",
    "recipientAccountNumber":"1020808489",
    "transactionReference":"prov9988zzjzj11| 000023211018133747005000003198",
    "transactionDateTime":"2021-10-18 13:32:28",
    "currency":"1",
    "responseMessage":" Approved or completed successfully",
    "responseCode":"00"
}


> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "amount":"100.00",
    "recipientBankCode":"000004",
    "recipientAccountNumber":"1020808489",
    "transactionReference":"prov9988zzjzj11| 000023211018133747005000003198",
    "transactionDateTime":"2021-10-18 13:32:28",
    "currency":"1",
    "responseMessage":" Approved or completed successfully",
    "responseCode":"00"
}


> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "amount":"100.00",
    "recipientBankCode":"000004",
    "recipientAccountNumber":"1020808489",
    "transactionReference":"prov9988zzjzj11| 000023211018133747005000003198",
    "transactionDateTime":"2021-10-18 13:32:28",
    "currency":"1",
    "responseMessage":" Approved or completed successfully",
    "responseCode":"00"
}


> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "amount":"100.00",
    "recipientBankCode":"000004",
    "recipientAccountNumber":"1020808489",
    "transactionReference":"prov9988zzjzj11| 000023211018133747005000003198",
    "transactionDateTime":"2021-10-18 13:32:28",
    "currency":"1",
    "responseMessage":" Approved or completed successfully",
    "responseCode":"00"
}


> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "amount":"100.00",
    "recipientBankCode":"000004",
    "recipientAccountNumber":"1020808489",
    "transactionReference":"prov9988zzjzj11| 000023211018133747005000003198",
    "transactionDateTime":"2021-10-18 13:32:28",
    "currency":"1",
    "responseMessage":" Approved or completed successfully",
    "responseCode":"00"
}


> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "amount":"100.00",
    "recipientBankCode":"000004",
    "recipientAccountNumber":"1020808489",
    "transactionReference":"prov9988zzjzj11| 000023211018133747005000003198",
    "transactionDateTime":"2021-10-18 13:32:28",
    "currency":"1",
    "responseMessage":" Approved or completed successfully",
    "responseCode":"00"
}
```

Last updated 1 year ago