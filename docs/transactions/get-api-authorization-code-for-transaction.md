# Get API authorization code for transaction

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

`GET /transaction/oauth/authorize/`

* * *

## 

[](#authorization-code)

Authorization Code.

`GET` `https://api-staging.providusbank.com/v1 /account/NIP`

Get API authorization code for transaction.

#### 

[](#headers)

Headers

Name

Type

Description

Content-Type

String

Request content type ( application/x-www-form-urlencoded )

#### 

[](#request-body)

Request Body

Name

Type

Description

response\_type\*

String

Response type. Value is `code`

client\_id

String

The OAuth client id

redirect\_uri

string

The OAuth client redirect URI ( must be URL encoded )

200 Successfully retrieved

[](#tab-id-200-successfully-retrieved)

401: Unauthorized Permission denied

[](#tab-id-401-unauthorized-permission-denied)

400: Bad Request The server cannot process the request due to a client error, such as malformed syntax or invalid parameters in the request.

[](#tab-id-400-bad-request-the-server-cannot-process-the-request-due-to-a-client-error-such-as-malformed-syntax)

500: Internal Server Error Server encountered an unexpected error

[](#tab-id-500-internal-server-error-server-encountered-an-unexpected-error)

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
curl --location --request POST 'https://mgw-staging.providusbank.com/transaction/oauth/authorize/' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--header 'Authorization: Basic NGNlMjQ5YmIzMTFmNGFlZWFmYzNlNDA2OTBjNzc4ZGM6WkRjMVlUbGxNRGd0WVdKa1lpMDBOalJqTFdKak5qUXROV0poTVRnMU16aGpZV1Zt' \
--data-urlencode 'grant_type=authorization_code' \
--data-urlencode 'client_id=091ddd8ca61c488aafcd078f2989eee0' \
--data-urlencode 'code=ZDc1YTllMDgtYWJkYi00NjRjLWJjNjQtNWJhMTg1MzhjYWVm' \
--data-urlencode 'redirect_uri=http%3A%2F%2F192.81.212.28%3A4003%2Foauth'
```

> The above command returns JSON structured like this:

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

[PreviousTransactions](/transactions)[NextExchange authorization code for access token](/transactions/exchange-authorization-code-for-access-token)