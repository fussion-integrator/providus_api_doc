# Get Providus Account

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

POST /GetProvidusAccount

* * *

## 

[](#providus-account)

Providus Account.

`POST` `https://api-staging.providusbank.com/v1/GetProvidusAccount`

Get Providus Account.

#### 

[](#request-body)

Request Body

Name

Type

Description

Username

string

Username of account owner

Password

string

Password of account owner

account\_number

String

account number for the account

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
curl --location 'https://api-staging.providusbank.com/GetProvidusAccount' \
--header 'Accept: application/json' \
--header 'Content-Type: application/json' \
--data '{
    "accountNumber": "1700263070",
    "userName" : "test",
    "password" : "test" 
}'
```

> The above command returns JSON structured like this:

```
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

```
import requests
import json

url = "https://api-staging.providusbank.com/GetProvidusAccount"

payload = json.dumps({
  "accountNumber": "1700263070",
  "userName": "test",
  "password": "test"
})
headers = {
  'Accept': 'application/json',
  'Content-Type': 'application/json'
}

response = requests.request("POST", url, headers=headers, data=payload)

print(response.text)
```

> The above command returns JSON structured like this:

```
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

```
OkHttpClient client = new OkHttpClient().newBuilder()
  .build();
MediaType mediaType = MediaType.parse("application/json");
RequestBody body = RequestBody.create(mediaType, "{\n    \"accountNumber\": \"1700263070\",\n    \"userName\" : \"test\",\n    \"password\" : \"test\" \n}");
Request request = new Request.Builder()
  .url("https://api-staging.providusbank.com/GetProvidusAccount")
  .method("POST", body)
  .addHeader("Accept", "application/json")
  .addHeader("Content-Type", "application/json")
  .build();
Response response = client.newCall(request).execute();
```

> The above command returns JSON structured like this:

```
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

```
var data = JSON.stringify({
  "accountNumber": "1700263070",
  "userName": "test",
  "password": "test"
});

var xhr = new XMLHttpRequest();
xhr.withCredentials = true;

xhr.addEventListener("readystatechange", function() {
  if(this.readyState === 4) {
    console.log(this.responseText);
  }
});

xhr.open("POST", "https://api-staging.providusbank.com/GetProvidusAccount");
xhr.setRequestHeader("Accept", "application/json");
xhr.setRequestHeader("Content-Type", "application/json");

xhr.send(data);
```

> The above command returns JSON structured like this:

```
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

```
<?php
require_once 'HTTP/Request2.php';
$request = new HTTP_Request2();
$request->setUrl('https://api-staging.providusbank.com/GetProvidusAccount');
$request->setMethod(HTTP_Request2::METHOD_POST);
$request->setConfig(array(
  'follow_redirects' => TRUE
));
$request->setHeader(array(
  'Accept' => 'application/json',
  'Content-Type' => 'application/json'
));
$request->setBody('{\n    "accountNumber": "1700263070",\n    "userName" : "test",\n    "password" : "test" \n}');
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

```
var options = new RestClientOptions("https://api-staging.providusbank.com")
{
  MaxTimeout = -1,
};
var client = new RestClient(options);
var request = new RestRequest("/GetProvidusAccount", Method.Post);
request.AddHeader("Accept", "application/json");
request.AddHeader("Content-Type", "application/json");
var body = @"{" + "\n" +
@"    ""accountNumber"": ""1700263070""," + "\n" +
@"    ""userName"" : ""test""," + "\n" +
@"    ""password"" : ""test"" " + "\n" +
@"}";
request.AddStringBody(body, DataFormat.Json);
RestResponse response = await client.ExecuteAsync(request);
Console.WriteLine(response.Content);
```

> The above command returns JSON structured like this:

```
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

[PreviousGet BVN Details](/payment/get-bvn-details)[NextGet NIP Transaction Status](/payment/get-nip-transaction-status)

Last updated 1 year ago