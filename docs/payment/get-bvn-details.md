1. Payment

# Get BVN Details

## Request Body

```json
{
  "Username": "\"Username_value\"",
  "Password": "\"Password_value\""
}
```

### Parameters

| Parameter | Type | Description |
|-----------|------|--------------|
| Username | string | Username of account owner |
| Password | string | Password of account owner |

Get the details of an account by bvn.

#### Test Base URL

https://api-staging.providusbank.com

#### Production Base URL

https://api.providusbank.com

#### HTTP Request

POST /account/bvn

## BVN Details.

`POST``https://api-staging.providusbank.com/v1/account/bvn`Get NIP Account.

#### Request Body





number

String

bvn number of account owner

### Sample Implementation

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap whitespace-pre-wrap
curl -x GET "https://api-demo.providusbank/account/NIP/banks"
  -H "Authorization: {{Authentication token}}"
  -H "Username: Username"
  -H "Password: Password"
inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "banks":[
        {"bankCode":"000014","bankName":"ACCESS BANK"},
        {"bankCode":"100013","bankName":"ACCESS MOBILE"},
        {"bankCode":"090133","bankName":"AL-BARAKAH MICROFINANCE BANK"},
        {"bankCode":"090116","bankName":"AMML MICROFINANCE BANK"},
        {"bankCode":"090001","bankName":"ASO SAVINGS"},
        {"bankCode":"090127","bankName":"BC KASH MICROFINANCE BANK"},
        {"bankCode":"090117","bankName":"BOCTRUST MICROFINANCE BANK LIMITED"},
        {"bankCode":"100005","bankName":"CELLULANT"},
        {"bankCode":"100015","bankName":"CHAMS MOBILE"},
        {"bankCode":"000009","bankName":"CITI BANK"},
        {"bankCode":"060001","bankName":"CORONATION BANK"},
        {"bankCode":"070006","bankName":"COVENANT MFB"},
        {"bankCode":"000005","bankName":"DIAMOND BANK"},
        {"bankCode":"100021","bankName":"EARTHOLEUM"},
        {"bankCode":"000010","bankName":"ECOBANK"},
        {"bankCode":"100008","bankName":"ECOBANK XPRESS ACCOUNT"},
        {"bankCode":"090114","bankName":"EMPIRE TRUST MICROFINANCE BANK"},
        {"bankCode":"000019","bankName":"ENTERPRISE BANK"},
        {"bankCode":"100006","bankName":"eTRANZACT"},
        {"bankCode":"060002","bankName":"FBN MERCHANT BANK"},
        {"bankCode":"100014","bankName":"FBN MOBILE"}
    ],
    "responseMessage":"SUCCESS",
    "responseCode":"00"}


> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "banks":[
        {"bankCode":"000014","bankName":"ACCESS BANK"},
        {"bankCode":"100013","bankName":"ACCESS MOBILE"},
        {"bankCode":"090133","bankName":"AL-BARAKAH MICROFINANCE BANK"},
        {"bankCode":"090116","bankName":"AMML MICROFINANCE BANK"},
        {"bankCode":"090001","bankName":"ASO SAVINGS"},
        {"bankCode":"090127","bankName":"BC KASH MICROFINANCE BANK"},
        {"bankCode":"090117","bankName":"BOCTRUST MICROFINANCE BANK LIMITED"},
        {"bankCode":"100005","bankName":"CELLULANT"},
        {"bankCode":"100015","bankName":"CHAMS MOBILE"},
        {"bankCode":"000009","bankName":"CITI BANK"},
        {"bankCode":"060001","bankName":"CORONATION BANK"},
        {"bankCode":"070006","bankName":"COVENANT MFB"},
        {"bankCode":"000005","bankName":"DIAMOND BANK"},
        {"bankCode":"100021","bankName":"EARTHOLEUM"},
        {"bankCode":"000010","bankName":"ECOBANK"},
        {"bankCode":"100008","bankName":"ECOBANK XPRESS ACCOUNT"},
        {"bankCode":"090114","bankName":"EMPIRE TRUST MICROFINANCE BANK"},
        {"bankCode":"000019","bankName":"ENTERPRISE BANK"},
        {"bankCode":"100006","bankName":"eTRANZACT"},
        {"bankCode":"060002","bankName":"FBN MERCHANT BANK"},
        {"bankCode":"100014","bankName":"FBN MOBILE"}
    ],
    "responseMessage":"SUCCESS",
    "responseCode":"00"}


> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "banks":[
        {"bankCode":"000014","bankName":"ACCESS BANK"},
        {"bankCode":"100013","bankName":"ACCESS MOBILE"},
        {"bankCode":"090133","bankName":"AL-BARAKAH MICROFINANCE BANK"},
        {"bankCode":"090116","bankName":"AMML MICROFINANCE BANK"},
        {"bankCode":"090001","bankName":"ASO SAVINGS"},
        {"bankCode":"090127","bankName":"BC KASH MICROFINANCE BANK"},
        {"bankCode":"090117","bankName":"BOCTRUST MICROFINANCE BANK LIMITED"},
        {"bankCode":"100005","bankName":"CELLULANT"},
        {"bankCode":"100015","bankName":"CHAMS MOBILE"},
        {"bankCode":"000009","bankName":"CITI BANK"},
        {"bankCode":"060001","bankName":"CORONATION BANK"},
        {"bankCode":"070006","bankName":"COVENANT MFB"},
        {"bankCode":"000005","bankName":"DIAMOND BANK"},
        {"bankCode":"100021","bankName":"EARTHOLEUM"},
        {"bankCode":"000010","bankName":"ECOBANK"},
        {"bankCode":"100008","bankName":"ECOBANK XPRESS ACCOUNT"},
        {"bankCode":"090114","bankName":"EMPIRE TRUST MICROFINANCE BANK"},
        {"bankCode":"000019","bankName":"ENTERPRISE BANK"},
        {"bankCode":"100006","bankName":"eTRANZACT"},
        {"bankCode":"060002","bankName":"FBN MERCHANT BANK"},
        {"bankCode":"100014","bankName":"FBN MOBILE"}
    ],
    "responseMessage":"SUCCESS",
    "responseCode":"00"}


> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "banks":[
        {"bankCode":"000014","bankName":"ACCESS BANK"},
        {"bankCode":"100013","bankName":"ACCESS MOBILE"},
        {"bankCode":"090133","bankName":"AL-BARAKAH MICROFINANCE BANK"},
        {"bankCode":"090116","bankName":"AMML MICROFINANCE BANK"},
        {"bankCode":"090001","bankName":"ASO SAVINGS"},
        {"bankCode":"090127","bankName":"BC KASH MICROFINANCE BANK"},
        {"bankCode":"090117","bankName":"BOCTRUST MICROFINANCE BANK LIMITED"},
        {"bankCode":"100005","bankName":"CELLULANT"},
        {"bankCode":"100015","bankName":"CHAMS MOBILE"},
        {"bankCode":"000009","bankName":"CITI BANK"},
        {"bankCode":"060001","bankName":"CORONATION BANK"},
        {"bankCode":"070006","bankName":"COVENANT MFB"},
        {"bankCode":"000005","bankName":"DIAMOND BANK"},
        {"bankCode":"100021","bankName":"EARTHOLEUM"},
        {"bankCode":"000010","bankName":"ECOBANK"},
        {"bankCode":"100008","bankName":"ECOBANK XPRESS ACCOUNT"},
        {"bankCode":"090114","bankName":"EMPIRE TRUST MICROFINANCE BANK"},
        {"bankCode":"000019","bankName":"ENTERPRISE BANK"},
        {"bankCode":"100006","bankName":"eTRANZACT"},
        {"bankCode":"060002","bankName":"FBN MERCHANT BANK"},
        {"bankCode":"100014","bankName":"FBN MOBILE"}
    ],
    "responseMessage":"SUCCESS",
    "responseCode":"00"}


> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "banks":[
        {"bankCode":"000014","bankName":"ACCESS BANK"},
        {"bankCode":"100013","bankName":"ACCESS MOBILE"},
        {"bankCode":"090133","bankName":"AL-BARAKAH MICROFINANCE BANK"},
        {"bankCode":"090116","bankName":"AMML MICROFINANCE BANK"},
        {"bankCode":"090001","bankName":"ASO SAVINGS"},
        {"bankCode":"090127","bankName":"BC KASH MICROFINANCE BANK"},
        {"bankCode":"090117","bankName":"BOCTRUST MICROFINANCE BANK LIMITED"},
        {"bankCode":"100005","bankName":"CELLULANT"},
        {"bankCode":"100015","bankName":"CHAMS MOBILE"},
        {"bankCode":"000009","bankName":"CITI BANK"},
        {"bankCode":"060001","bankName":"CORONATION BANK"},
        {"bankCode":"070006","bankName":"COVENANT MFB"},
        {"bankCode":"000005","bankName":"DIAMOND BANK"},
        {"bankCode":"100021","bankName":"EARTHOLEUM"},
        {"bankCode":"000010","bankName":"ECOBANK"},
        {"bankCode":"100008","bankName":"ECOBANK XPRESS ACCOUNT"},
        {"bankCode":"090114","bankName":"EMPIRE TRUST MICROFINANCE BANK"},
        {"bankCode":"000019","bankName":"ENTERPRISE BANK"},
        {"bankCode":"100006","bankName":"eTRANZACT"},
        {"bankCode":"060002","bankName":"FBN MERCHANT BANK"},
        {"bankCode":"100014","bankName":"FBN MOBILE"}
    ],
    "responseMessage":"SUCCESS",
    "responseCode":"00"}


> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "banks":[
        {"bankCode":"000014","bankName":"ACCESS BANK"},
        {"bankCode":"100013","bankName":"ACCESS MOBILE"},
        {"bankCode":"090133","bankName":"AL-BARAKAH MICROFINANCE BANK"},
        {"bankCode":"090116","bankName":"AMML MICROFINANCE BANK"},
        {"bankCode":"090001","bankName":"ASO SAVINGS"},
        {"bankCode":"090127","bankName":"BC KASH MICROFINANCE BANK"},
        {"bankCode":"090117","bankName":"BOCTRUST MICROFINANCE BANK LIMITED"},
        {"bankCode":"100005","bankName":"CELLULANT"},
        {"bankCode":"100015","bankName":"CHAMS MOBILE"},
        {"bankCode":"000009","bankName":"CITI BANK"},
        {"bankCode":"060001","bankName":"CORONATION BANK"},
        {"bankCode":"070006","bankName":"COVENANT MFB"},
        {"bankCode":"000005","bankName":"DIAMOND BANK"},
        {"bankCode":"100021","bankName":"EARTHOLEUM"},
        {"bankCode":"000010","bankName":"ECOBANK"},
        {"bankCode":"100008","bankName":"ECOBANK XPRESS ACCOUNT"},
        {"bankCode":"090114","bankName":"EMPIRE TRUST MICROFINANCE BANK"},
        {"bankCode":"000019","bankName":"ENTERPRISE BANK"},
        {"bankCode":"100006","bankName":"eTRANZACT"},
        {"bankCode":"060002","bankName":"FBN MERCHANT BANK"},
        {"bankCode":"100014","bankName":"FBN MOBILE"}
    ],
    "responseMessage":"SUCCESS",
    "responseCode":"00"}
```

Last updated 1 year ago