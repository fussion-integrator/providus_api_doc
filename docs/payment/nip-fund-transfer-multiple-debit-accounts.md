# NIP Fund Transfer Multiple Debit Accounts

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

POST /NIPFundTransferMultipleDebitAccounts

* * *

## 

[](#nip-bank)

NIP Bank.

`POST` `https://api-staging.providusbank.com/v1/NIPFundTransferMultipleDebitAccounts`

NIP Fund Transfer Multiple Debit Accounts.

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

debitAccount\*

String

sourceAccountName\*

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
curl --location 'https://api-staging.providusbank.com/NIPFundTransferMultipleDebitAccounts' \
--header 'Accept: application/json' \
--header 'Content-Type: application/json' \
--data '{
"beneficiaryAccountName":"Nathan Agbara", "transactionAmount": "50",
"currencyCode":"NGN",
"narration":"Testing", "debitAccount":"5900235871", "sourceAccountName":"NATHAN AGBARA" , "beneficiaryAccountNumber":"0430294874", "beneficiaryBank":"000013", "transactionReference":"SDFGHJUKJ456UKJH34565", "userName":"test",
"password":"test"
}'
```

> The above command returns JSON structured like this:

Copy

```
{
    "transactionReference": "35326323fghn", 
    "responseMessage": " Approved or completed successfully", 
    "responseCode": "00"
}
```

Copy

```
import requests
import json

url = "https://api-staging.providusbank.com/NIPFundTransferMultipleDebitAccounts"

payload = json.dumps({
  "beneficiaryAccountName": "Nathan Agbara",
  "transactionAmount": "50",
  "currencyCode": "NGN",
  "narration": "Testing",
  "debitAccount": "5900235871",
  "sourceAccountName": "NATHAN AGBARA",
  "beneficiaryAccountNumber": "0430294874",
  "beneficiaryBank": "000013",
  "transactionReference": "SDFGHJUKJ456UKJH34565",
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
    "transactionReference": "35326323fghn", 
    "responseMessage": " Approved or completed successfully", 
    "responseCode": "00"
}
```

Copy

```
OkHttpClient client = new OkHttpClient().newBuilder()
  .build();
MediaType mediaType = MediaType.parse("application/json");
RequestBody body = RequestBody.create(mediaType, "{\n\"beneficiaryAccountName\":\"Nathan Agbara\", \"transactionAmount\": \"50\",\n\"currencyCode\":\"NGN\",\n\"narration\":\"Testing\", \"debitAccount\":\"5900235871\", \"sourceAccountName\":\"NATHAN AGBARA\" , \"beneficiaryAccountNumber\":\"0430294874\", \"beneficiaryBank\":\"000013\", \"transactionReference\":\"SDFGHJUKJ456UKJH34565\", \"userName\":\"test\",\n\"password\":\"test\"\n}");
Request request = new Request.Builder()
  .url("https://api-staging.providusbank.com/NIPFundTransferMultipleDebitAccounts")
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
    "transactionReference": "35326323fghn", 
    "responseMessage": " Approved or completed successfully", 
    "responseCode": "00"
}
```

Copy

```
var data = JSON.stringify({
  "beneficiaryAccountName": "Nathan Agbara",
  "transactionAmount": "50",
  "currencyCode": "NGN",
  "narration": "Testing",
  "debitAccount": "5900235871",
  "sourceAccountName": "NATHAN AGBARA",
  "beneficiaryAccountNumber": "0430294874",
  "beneficiaryBank": "000013",
  "transactionReference": "SDFGHJUKJ456UKJH34565",
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

xhr.open("POST", "https://api-staging.providusbank.com/NIPFundTransferMultipleDebitAccounts");
xhr.setRequestHeader("Accept", "application/json");
xhr.setRequestHeader("Content-Type", "application/json");

xhr.send(data);
```

> The above command returns JSON structured like this:

Copy

```
{
    "transactionReference": "35326323fghn", 
    "responseMessage": " Approved or completed successfully", 
    "responseCode": "00"
}
```

Copy

```
<?php
require_once 'HTTP/Request2.php';
$request = new HTTP_Request2();
$request->setUrl('https://api-staging.providusbank.com/NIPFundTransferMultipleDebitAccounts');
$request->setMethod(HTTP_Request2::METHOD_POST);
$request->setConfig(array(
  'follow_redirects' => TRUE
));
$request->setHeader(array(
  'Accept' => 'application/json',
  'Content-Type' => 'application/json'
));
$request->setBody('{\n"beneficiaryAccountName":"Nathan Agbama", "transactionAmount": "50",\n"currencyCode":"NGN",\n"narration":"Testing", "debitAccount":"5980235871", "sourceAccountName":"NATHAN AGBARA" , "beneficiaryAccountNumber":"0430234874", "beneficiaryBank":"000013", "transactionReference":"SDFGHJUKJ456UKJH34565", "userName":"test",\n"password":"test"\n}');
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
    "transactionReference": "35326323fghn", 
    "responseMessage": " Approved or completed successfully", 
    "responseCode": "00"
}
```

Copy

```
var options = new RestClientOptions("https://api-staging.providusbank.com")
{
  MaxTimeout = -1,
};
var client = new RestClient(options);
var request = new RestRequest("/NIPFundTransferMultipleDebitAccounts", Method.Post);
request.AddHeader("Accept", "application/json");
request.AddHeader("Content-Type", "application/json");
var body = @"{" + "\n" +
@"""beneficiaryAccountName"":""Nathan Agbara"", ""transactionAmount"": ""50""," + "\n" +
@"""currencyCode"":""NGN""," + "\n" +
@"""narration"":""Testing"", ""debitAccount"":""5900235871"", ""sourceAccountName"":""NATHAN AGBARA"" , ""beneficiaryAccountNumber"":""0430294874"", ""beneficiaryBank"":""000013"", ""transactionReference"":""SDFGHJUKJ456UKJH34565"", ""userName"":""test""," + "\n" +
@"""password"":""test""" + "\n" +
@"}";
request.AddStringBody(body, DataFormat.Json);
RestResponse response = await client.ExecuteAsync(request);
Console.WriteLine(response.Content);
```

> The above command returns JSON structured like this:

Copy

```
{
    "transactionReference": "35326323fghn", 
    "responseMessage": " Approved or completed successfully", 
    "responseCode": "00"
}
```

[PreviousGet Providus Transaction Status](/payment/get-providus-transaction-status)[NextNIP Fund Transfer](/payment/nip-fund-transfer)

Last updated 1 year ago