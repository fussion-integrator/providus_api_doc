1. Account

# Retrieve Account Number

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

Retrieve an Account number.

#### Test Base URL

https://api-staging.providusbank.com

#### Production Base URL

https://api.providusbank.com

#### HTTP Request

GET /account/account

## Providus Account.

`GET``https://api-staging.providusbank.com/v1/account`Get NIP Account.

#### Request Body





account_number

String

account number for the account

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "accountStatus":"ACTIVE",
    "emailAddress":"[email protected]",
    "phoneNumber":"08054477605",
    "accountName":"CHARLY ODUMODU BLACK",
    "bvn":"22100477606",
    "accountNumber":"5900043856",
    "cbaCustomerID":"45139",
    "responseMessage":"SUCCESSFUL",
    "availableBalance":"468520.951",
    "responseCode":"00"
}
inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap whitespace-pre-wrap
curl -x GET "https://api-demo.providusbank/account/?account_number=00017000" 
  -H "Authorization: {{Authentication token}}"
  -H "Username: Username"
  -H "Password: Password"
inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "accountStatus":"ACTIVE",
    "emailAddress":"[email protected]",
    "phoneNumber":"08054477605",
    "accountName":"CHARLY ODUMODU BLACK",
    "bvn":"22100477606",
    "accountNumber":"5900043856",
    "cbaCustomerID":"45139",
    "responseMessage":"SUCCESSFUL",
    "availableBalance":"468520.951",
    "responseCode":"00"
}


> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "accountStatus":"ACTIVE",
    "emailAddress":"[email protected]",
    "phoneNumber":"08054477605",
    "accountName":"CHARLY ODUMODU BLACK",
    "bvn":"22100477606",
    "accountNumber":"5900043856",
    "cbaCustomerID":"45139",
    "responseMessage":"SUCCESSFUL",
    "availableBalance":"468520.951",
    "responseCode":"00"
}


> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "accountStatus":"ACTIVE",
    "emailAddress":"[email protected]",
    "phoneNumber":"08054477605",
    "accountName":"CHARLY ODUMODU BLACK",
    "bvn":"22100477606",
    "accountNumber":"5900043856",
    "cbaCustomerID":"45139",
    "responseMessage":"SUCCESSFUL",
    "availableBalance":"468520.951",
    "responseCode":"00"
}


> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "accountStatus":"ACTIVE",
    "emailAddress":"[email protected]",
    "phoneNumber":"08054477605",
    "accountName":"CHARLY ODUMODU BLACK",
    "bvn":"22100477606",
    "accountNumber":"5900043856",
    "cbaCustomerID":"45139",
    "responseMessage":"SUCCESSFUL",
    "availableBalance":"468520.951",
    "responseCode":"00"
}


> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "accountStatus":"ACTIVE",
    "emailAddress":"[email protected]",
    "phoneNumber":"08054477605",
    "accountName":"CHARLY ODUMODU BLACK",
    "bvn":"22100477606",
    "accountNumber":"5900043856",
    "cbaCustomerID":"45139",
    "responseMessage":"SUCCESSFUL",
    "availableBalance":"468520.951",
    "responseCode":"00"
}


> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "accountStatus":"ACTIVE",
    "emailAddress":"[email protected]",
    "phoneNumber":"08054477605",
    "accountName":"CHARLY ODUMODU BLACK",
    "bvn":"22100477606",
    "accountNumber":"5900043856",
    "cbaCustomerID":"45139",
    "responseMessage":"SUCCESSFUL",
    "availableBalance":"468520.951",
    "responseCode":"00"
}
```

Last updated 10 days ago

## Sample Implementation

```curl
curl -X GET "/api/v1/account/number" \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json"
```

```python
import requests

url = "/api/v1/account/number"
headers = {
    "Authorization": "Bearer YOUR_API_KEY",
    "Content-Type": "application/json"
}

response = requests.get(url, headers=headers)
print(response.json())
```

```javascript
const response = await fetch('/api/v1/account/number', {
  method: 'GET',
  headers: {
    'Authorization': 'Bearer YOUR_API_KEY',
    'Content-Type': 'application/json'
  }
});

const data = await response.json();
console.log(data);
```

```php
<?php
$url = "/api/v1/account/number";
$headers = [
    "Authorization: Bearer YOUR_API_KEY",
    "Content-Type: application/json"
];

$context = stream_context_create([
    'http' => [
        'method' => 'GET',
        'header' => implode("\r\n", $headers)
    ]
]);

$response = file_get_contents($url, false, $context);
echo $response;
?>
```

