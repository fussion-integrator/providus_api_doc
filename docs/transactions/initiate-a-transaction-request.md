# Initiate a Transaction Request

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

GET /account/NIP

* * *

## 

[](#nip-account)

NIP Account.

`GET` `https://api-staging.providusbank.com/v1 /account/NIP`

Get NIP Account.

#### 

[](#request-body)

Request Body

Name

Type

Description

account\_number\*

string

account number for the account

bank\_code

string

code of the bank

Username

string

Username of account owner

Password

string

Password of account owner

200 Account successfully retrieved

[](#tab-id-200-account-successfully-retrieved)

401: Unauthorized Permission denied

[](#tab-id-401-unauthorized-permission-denied)

400: Bad Request The server cannot process the request due to a client error, such as malformed syntax or invalid parameters in the request.

[](#tab-id-400-bad-request-the-server-cannot-process-the-request-due-to-a-client-error-such-as-malformed-syntax)

500: Internal Server Error Server encountered an unexpected error

[](#tab-id-500-internal-server-error-server-encountered-an-unexpected-error)

```
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

```
curl -x GET "https://api-staging.providusbank.com/account/NIP?account_number=3041004406&bank_code=57"
  -H "Authorization: {{Authentication token}}"
  -H "Username: Username"
  -H "Password: Password"
```

> The above command returns JSON structured like this:

```
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

```
import requests
from requests.structures import CaseInsensitiveDict
url = "https://api-staging.providusbank.com/account/NIP?account_number=3041004406&bank_code=57"
headers = CaseInsensitiveDict()
headers["Authorization"] = "{{Authentication token}}"
headers["Username"] = "Username"
headers["Password"] = "Password"
resp = requests.get(url, headers=headers)
print(resp.status_code)
```

> The above command returns JSON structured like this:

```
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

```
URL url = new URL("https://api-staging.providusbank.com/account/NIP?account_number=3041004406&bank_code=57");
HttpURLConnection http = (HttpURLConnection)url.openConnection();
http.setRequestProperty("Authorization", "{{Authentication token}}");
http.setRequestProperty("Username", "Username");
http.setRequestProperty("Password", "Password");
System.out.println(http.getResponseCode() + " " + http.getResponseMessage());
http.disconnect();
```

> The above command returns JSON structured like this:

```
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

```
var xhr = new XMLHttpRequest();
xhr.withCredentials = true;

xhr.addEventListener("readystatechange", function() {
  if(this.readyState === 4) {
    console.log(this.responseText);
  }
});
xhr.open("GET", "https://api-staging.providusbank.com/account/NIP?account_number=3041004406&bank_code=57");
xhr.setRequestHeader("Authorization", "{{Authentication token}}");
xhr.setRequestHeader("Username", "Username");
xhr.setRequestHeader("Password", "Password");
xhr.send();
```

> The above command returns JSON structured like this:

```
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

```
<?php
require_once 'HTTP/Request2.php';
$request = new HTTP_Request2();
$request->setUrl('https://api-staging.providusbank.com/account/NIP?account_number=3041004406&bank_code=57');
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

```
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

```
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

```
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

[PreviousGet Transaction Status](/transactions/get-transaction-status)[NextProvi Bill](/provi-bill)

Last updated 1 year ago