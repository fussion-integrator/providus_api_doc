# Providus Fund Transfer

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

POST /ProvidusFundTransfer

* * *

## 

[](#providus-fund-transfer)

Providus Fund Transfer.

`POST` `https://api-staging.providusbank.com/v1/NIPFundTransfer`

Transfer fund using providus.

#### 

[](#headers)

Headers

Name

Type

Description

Accept\*

application/json

Content-Type\*

application/json

#### 

[](#request-body)

Request Body

Name

Type

Description

transactionAmount\*

String

currencyCode\*

String

beneficiaryAccountName\*

String

narration

String

sourceAccountName

String

beneficiaryAccountNumber\*

String

beneficiaryBank\*

String

transactionReference\*

String

userName\*

String

password\*

String

200 Status successfully retrieved

[](#tab-id-200-status-successfully-retrieved)

401: Unauthorized Permission denied

[](#tab-id-401-unauthorized-permission-denied)

400: Bad Request The server cannot process the request due to a client error, such as malformed syntax or invalid parameters in the request.

[](#tab-id-400-bad-request-the-server-cannot-process-the-request-due-to-a-client-error-such-as-malformed-syntax)

500: Internal Server Error Server encountered an unexpected error

[](#tab-id-500-internal-server-error-server-encountered-an-unexpected-error)

Copy

```
{
    "transactionReference": "20191119143854",
    "sessionId": "999037230913163757005000082268", 
    "responseMessage": " Approved or completed successfully", 
    "responseCode": "00"
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

Copy

```
curl --location 'https://api-staging.providusbank.com/ProvidusFundTransfer' \
--header 'Accept: application/json' \
--header 'Content-Type: application/json' \
--data '{ "creditAccount":"5900174721", "debitAccount":"1700313889",
"transactionAmount": "2000.45", "currencyCode":"NGN", "narration":"Testing", "transactionReference":"20191119143501", "userName":"test",
"password":"test" }'
```

> The above command returns JSON structured like this:

Copy

```
{
    "amount":"100.0", 
    "transactionReference":"2345677777", 
    "currency":"NGN", 
    "responseMessage":"OPERATION SUCCESSFUL", 
    "responseCode":"00"
}
```

Copy

```
import requests
import json

url = "https://api-staging.providusbank.com/ProvidusFundTransfer"

payload = json.dumps({
  "creditAccount": "5900174721",
  "debitAccount": "1700313889",
  "transactionAmount": "2000.45",
  "currencyCode": "NGN",
  "narration": "Testing",
  "transactionReference": "20191119143501",
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

Copy

```
{
    "amount":"100.0", 
    "transactionReference":"2345677777", 
    "currency":"NGN", 
    "responseMessage":"OPERATION SUCCESSFUL", 
    "responseCode":"00"
}
```

Copy

```
OkHttpClient client = new OkHttpClient().newBuilder()
  .build();
MediaType mediaType = MediaType.parse("application/json");
RequestBody body = RequestBody.create(mediaType, "{ \"creditAccount\":\"5900174721\", \"debitAccount\":\"1700313889\",\n\"transactionAmount\": \"2000.45\", \"currencyCode\":\"NGN\", \"narration\":\"Testing\", \"transactionReference\":\"20191119143501\", \"userName\":\"test\",\n\"password\":\"test\" }");
Request request = new Request.Builder()
  .url("https://api-staging.providusbank.com/ProvidusFundTransfer")
  .method("POST", body)
  .addHeader("Accept", "application/json")
  .addHeader("Content-Type", "application/json")
  .build();
Response response = client.newCall(request).execute();
```

> The above command returns JSON structured like this:

Copy

```
{
    "amount":"100.0", 
    "transactionReference":"2345677777", 
    "currency":"NGN", 
    "responseMessage":"OPERATION SUCCESSFUL", 
    "responseCode":"00"
}
```

Copy

```
var data = JSON.stringify({
  "creditAccount": "5900174721",
  "debitAccount": "1700313889",
  "transactionAmount": "2000.45",
  "currencyCode": "NGN",
  "narration": "Testing",
  "transactionReference": "20191119143501",
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

xhr.open("POST", "https://api-staging.providusbank.com/ProvidusFundTransfer");
xhr.setRequestHeader("Accept", "application/json");
xhr.setRequestHeader("Content-Type", "application/json");

xhr.send(data);
```

> The above command returns JSON structured like this:

Copy

```
{
    "amount":"100.0", 
    "transactionReference":"2345677777", 
    "currency":"NGN", 
    "responseMessage":"OPERATION SUCCESSFUL", 
    "responseCode":"00"
}
```

Copy

```
<?php
require_once 'HTTP/Request2.php';
$request = new HTTP_Request2();
$request->setUrl('https://api-staging.providusbank.com/ProvidusFundTransfer');
$request->setMethod(HTTP_Request2::METHOD_POST);
$request->setConfig(array(
  'follow_redirects' => TRUE
));
$request->setHeader(array(
  'Accept' => 'application/json',
  'Content-Type' => 'application/json'
));
$request->setBody('{ "creditAccount":"5900174721", "debitAccount":"1700313889",\n"transactionAmount": "2000.45", "currencyCode":"NGN", "narration":"Testing", "transactionReference":"20191119143501", "userName":"test",\n"password":"test" }');
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

Copy

```
{
    "amount":"100.0", 
    "transactionReference":"2345677777", 
    "currency":"NGN", 
    "responseMessage":"OPERATION SUCCESSFUL", 
    "responseCode":"00"
}
```

Copy

```
var options = new RestClientOptions("https://api-staging.providusbank.com")
{
  MaxTimeout = -1,
};
var client = new RestClient(options);
var request = new RestRequest("/ProvidusFundTransfer", Method.Post);
request.AddHeader("Accept", "application/json");
request.AddHeader("Content-Type", "application/json");
var body = @"{ ""creditAccount"":""5900174721"", ""debitAccount"":""1700313889""," + "\n" +
@"""transactionAmount"": ""2000.45"", ""currencyCode"":""NGN"", ""narration"":""Testing"", ""transactionReference"":""20191119143501"", ""userName"":""test""," + "\n" +
@"""password"":""test"" }";
request.AddStringBody(body, DataFormat.Json);
RestResponse response = await client.ExecuteAsync(request);
Console.WriteLine(response.Content);
```

> The above command returns JSON structured like this:

Copy

```
{
    "amount":"100.0", 
    "transactionReference":"2345677777", 
    "currency":"NGN", 
    "responseMessage":"OPERATION SUCCESSFUL", 
    "responseCode":"00"
}
```

[PreviousNIP Fund Transfer](/payment/nip-fund-transfer)[NextTransactions](/transactions)

Last updated 1 year ago