# Get Providus Transaction Status

* * *

#### 

[](#test-base-url)

Test Base URL

[https://api-staging.providusbank.com](https://api-staging.providusbank.com

)

#### 

[](#production-base-url)

Production Base URL

[https://api.providusbank.com](https://api.providusbank.com)

#### 

[](#http-request)

HTTP Request

POST /payment/status

* * *

## 

[](#nip-bank)

NIP Bank.

`POST` `https://api-staging.providusbank.com/v1/account/NIP/banks`

Get Providus transactions by status.

#### 

[](#request-body)

Request Body

Name

Type

Description

userName

String

Username of account owner

password

String

Password of account owner

transactionReference

String

Reference to the transaction

200 Status successfully retrieved

[](#tab-id-200-status-successfully-retrieved)

401: Unauthorized Permission denied

[](#tab-id-401-unauthorized-permission-denied)

400: Bad Request The server cannot process the request due to a client error, such as malformed syntax or invalid parameters in the request.

[](#tab-id-400-bad-request-the-server-cannot-process-the-request-due-to-a-client-error-such-as-malformed-syntax)

500: Internal Server Error Server encountered an unexpected error

[](#tab-id-500-internal-server-error-server-encountered-an-unexpected-error)

Copy

* * *

### 

[](#sample-implementation)

Sample Implementation

Curl

[](#tab-curl)

Python

[](#tab-python)

Java

[](#tab-java)

JavaScript

[](#tab-javascript)

PHP

[](#tab-php)

C#

[](#tab-c)

Copy

```
curl -x GET "https://api-staging.providusbank.com/payment/status?transactionReference=prov9988zzjzj11"
  -H "Authorization: {{Authentication token}}"
  -H "userName: userName"
  -H "password: password"
```

> The above command returns JSON structured like this:

Copy

```
{
    "amount":"100.0",
    "creditAccount":"1700263070",
    "debitAccount":"5900085856", "transactionReference":"2345677777", "transactionDateTime":"2020-05-04 14:12:11.0", "currency":"NGN", "responseMessage":
    "OPERATION SUCCESSFUL",
    "responseCode":"00"
}
```

Copy

```
import requests
from requests.structures import CaseInsensitiveDict

url = "https://api-staging.providusbank.com/payment/NIP/status?transactionReference=prov9988zzjzj11"

headers = CaseInsensitiveDict()
headers["Authorization"] = "{{Authentication token}}"
headers["userName"] = "userName"
headers["password"] = "password"

resp = requests.get(url, headers=headers)

print(resp.status_code)
```

> The above command returns JSON structured like this:

Copy

```
{
    "amount":"100.0",
    "creditAccount":"1700263070",
    "debitAccount":"5900085856", "transactionReference":"2345677777", "transactionDateTime":"2020-05-04 14:12:11.0", "currency":"NGN", "responseMessage":
    "OPERATION SUCCESSFUL",
    "responseCode":"00"
}
```

Copy

```
URL url = new URL("https://api-staging.providusbank.com/payment/NIP/status?transactionReference=prov9988zzjzj11");
HttpURLConnection http = (HttpURLConnection)url.openConnection();
http.setRequestProperty("Authorization", "{{Authentication token}}");
http.setRequestProperty("userName", "Username");
http.setRequestProperty("password", "Password");

System.out.println(http.getResponseCode() + " " + http.getResponseMessage());
http.disconnect();
```

> The above command returns JSON structured like this:

Copy

```
{
    "amount":"100.0",
    "creditAccount":"1700263070",
    "debitAccount":"5900085856", "transactionReference":"2345677777", "transactionDateTime":"2020-05-04 14:12:11.0", "currency":"NGN", "responseMessage":
    "OPERATION SUCCESSFUL",
    "responseCode":"00"
}
```

Copy

```
var xhr = new XMLHttpRequest();
xhr.withCredentials = true;

xhr.addEventListener("readystatechange", function() {
  if(this.readyState === 4) {
    console.log(this.responseText);
  }
});
xhr.open("GET", "https://api-staging.providusbank.com/payment/NIP/status?transactionReference=prov9988zzjzj11");
xhr.setRequestHeader("Authorization", "{{Authentication token}}");
xhr.setRequestHeader("userName", "Username");
xhr.setRequestHeader("password", "Password");
xhr.send();
```

> The above command returns JSON structured like this:

Copy

```
{
    "amount":"100.0",
    "creditAccount":"1700263070",
    "debitAccount":"5900085856", "transactionReference":"2345677777", "transactionDateTime":"2020-05-04 14:12:11.0", "currency":"NGN", "responseMessage":
    "OPERATION SUCCESSFUL",
    "responseCode":"00"
}
```

Copy

```
<?php
require_once 'HTTP/Request2.php';
$request = new HTTP_Request2();
$request->setUrl('https://api-staging.providusbank.com/payment/NIP/status?transactionReference=prov9988zzjzj11');
$request->setMethod(HTTP_Request2::METHOD_GET);
$request->setConfig(array(
  'follow_redirects' => TRUE
));
$request->setHeader(array(
  'Authorization' => '{{Authentication token}}',
  'userName' => 'Username',
  'password' => 'Password'
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
?>
```

> The above command returns JSON structured like this:

Copy

```
{
    "amount":"100.0",
    "creditAccount":"1700263070",
    "debitAccount":"5900085856", "transactionReference":"2345677777", "transactionDateTime":"2020-05-04 14:12:11.0", "currency":"NGN", "responseMessage":
    "OPERATION SUCCESSFUL",
    "responseCode":"00"
}
```

Copy

```
var client = new RestClient("https://api-staging.providusbank.com/payment/NIP/status?transactionReference=prov9988zzjzj11");
client.Timeout = -1;
var request = new RestRequest(Method.GET);
request.AddHeader("Authorization", "{{Authentication token}}");
request.AddHeader("userName", "Username");
request.AddHeader("password", "Password");
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

> The above command returns JSON structured like this:

Copy

```
{
    "amount":"100.0",
    "creditAccount":"1700263070",
    "debitAccount":"5900085856", "transactionReference":"2345677777", "transactionDateTime":"2020-05-04 14:12:11.0", "currency":"NGN", "responseMessage":
    "OPERATION SUCCESSFUL",
    "responseCode":"00"
}
```

[PreviousGet NIP Transaction Status](/payment/get-nip-transaction-status)[NextNIP Fund Transfer Multiple Debit Accounts](/payment/nip-fund-transfer-multiple-debit-accounts)

Last updated 1 year ago