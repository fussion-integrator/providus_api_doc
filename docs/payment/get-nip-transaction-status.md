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
```

### Sample Implementation

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap whitespace-pre-wrap
curl -x GET "https://api-staging.providusbank.com/payment/NIP/status?transaction_reference=prov9988zzjzj11"
  -H "Authorization: {{Authentication token}}"
  -H "Username: Username"
  -H "Password: Password"
```

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

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
import requests
from requests.structures import CaseInsensitiveDict

url = "https://api-staging.providusbank.com/payment/NIP/status?transaction_reference=prov9988zzjzj11"

headers = CaseInsensitiveDict()
headers["Authorization"] = "{{Authentication token}}"
headers["Username"] = "Username"
headers["Password"] = "Password"


resp = requests.get(url, headers=headers)

print(resp.status_code)
```

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

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
URL url = new URL("https://api-staging.providusbank.com/payment/NIP/status?transaction_reference=prov9988zzjzj11");
HttpURLConnection http = (HttpURLConnection)url.openConnection();
http.setRequestProperty("Authorization", "{{Authentication token}}");
http.setRequestProperty("Username", "Username");
http.setRequestProperty("Password", "Password");

System.out.println(http.getResponseCode() + " " + http.getResponseMessage());
http.disconnect();
```

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

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
var xhr = new XMLHttpRequest();
xhr.withCredentials = true;

xhr.addEventListener("readystatechange", function() {
  if(this.readyState === 4) {
    console.log(this.responseText);
  }
});
xhr.open("GET", "https://api-staging.providusbank.com/payment/NIP/status?transaction_reference=prov9988zzjzj11");
xhr.setRequestHeader("Authorization", "{{Authentication token}}");
xhr.setRequestHeader("Username", "Username");
xhr.setRequestHeader("Password", "Password");
xhr.send();
```

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

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
<?php
require_once 'HTTP/Request2.php';
$request = new HTTP_Request2();
$request->setUrl('https://api-staging.providusbank.com/payment/NIP/status?transaction_reference=prov9988zzjzj11');
$request->setMethod(HTTP_Request2::METHOD_GET);
$request->setConfig(array(
  'follow_redirects' => TRUE
));
$request->setHeader(array(
  'Authorization' => '{{Authentication token}}',
  'Username' => 'Username',
  'Password' => 'Password'
));
try {
  $response = $request->send();
  if ($response->getStatus() == 200) {
    echo $response->getBody();
  }
  else {
    echo 'Unexpected HTTP status: ' . $response->getStatus() . ' ' .
    $response->getReasonPhrase();
  }
}
catch(HTTP_Request2_Exception $e) {
  echo 'Error: ' . $e->getMessage();
}
```

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

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
var client = new RestClient("https://api-staging.providusbank.com/account/NIP?account_number=3041004406&bank_code=57");
client.Timeout = -1;
var request = new RestRequest(Method.GET);
request.AddHeader("Authorization", "{{Authentication token}}");
request.AddHeader("Username", "Username");
request.AddHeader("Password", "Password");
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

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