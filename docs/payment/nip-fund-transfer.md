1. Payment

# NIP Fund Transfer

Get the status of a transaction .

#### Test Base URL

https://api-staging.providusbank.com

#### Production Base URL

https://api.providusbank.com

#### HTTP Request

POST /NIPFundTransfer

## NIP Bank.

`POST``https://api-staging.providusbank.com/v1/NIPFundTransfer`NIP Fund Transfer.

#### Headers

Accept*

application/json

Content-Type*

application/json

#### Request Body

transactionAmount*

String

currencyCode*

String

beneficiaryAccountName*

String

narration

String

sourceAccountName

String

beneficiaryAccountNumber*

String

beneficiaryBank*

String

transactionReference*

String

userName*

String

password*

String

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "transactionReference": "20191119143854",
    "sessionId": "999037230913163757005000082268", 
    "responseMessage": " Approved or completed successfully", 
    "responseCode": "00"
}
```

### Sample Implementation

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap whitespace-pre-wrap
curl --location 'https://api-staging.providusbank.com/NIPFundTransfer' \
--header 'Accept: application/json' \
--header 'Content-Type: application/json' \
--data '{
"beneficiaryAccountName":"UGBO, CHARLES UMORE", "transactionAmount": "2000.45", "currencyCode":"NGN",
"narration":"Testing",
"sourceAccountName":"Nnamdi Adebayo Hamzat" , "beneficiaryAccountNumber":"0045434120", "beneficiaryBank":"000013", "transactionReference":"20191119143854", "userName":"test",
"password":"test"
}'

```

> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "transactionReference": "20191119143854",
    "sessionId": "999037230913163757005000082268", 
    "responseMessage": " Approved or completed successfully", 
    "responseCode": "00"
}
```

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
import requests
import json

url = "https://api-staging.providusbank.com/NIPFundTransfer"

payload = json.dumps({
  "beneficiaryAccountName": "UGBO, CHARLES UMORE",
  "transactionAmount": "2000.45",
  "currencyCode": "NGN",
  "narration": "Testing",
  "sourceAccountName": "Nnamdi Adebayo Hamzat",
  "beneficiaryAccountNumber": "0045434120",
  "beneficiaryBank": "000013",
  "transactionReference": "20191119143854",
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

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "transactionReference": "20191119143854",
    "sessionId": "999037230913163757005000082268", 
    "responseMessage": " Approved or completed successfully", 
    "responseCode": "00"
}
```

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
OkHttpClient client = new OkHttpClient().newBuilder()
  .build();
MediaType mediaType = MediaType.parse("application/json");
RequestBody body = RequestBody.create(mediaType, "{\n\"beneficiaryAccountName\":\"UGBO, CHARLES UMORE\", \"transactionAmount\": \"2000.45\", \"currencyCode\":\"NGN\",\n\"narration\":\"Testing\",\n\"sourceAccountName\":\"Nnamdi Adebayo Hamzat\" , \"beneficiaryAccountNumber\":\"0045434120\", \"beneficiaryBank\":\"000013\", \"transactionReference\":\"20191119143854\", \"userName\":\"test\",\n\"password\":\"test\"\n}");
Request request = new Request.Builder()
  .url("https://api-staging.providusbank.com/NIPFundTransfer")
  .method("POST", body)
  .addHeader("Accept", "application/json")
  .addHeader("Content-Type", "application/json")
  .build();
Response response = client.newCall(request).execute();
```

> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "transactionReference": "20191119143854",
    "sessionId": "999037230913163757005000082268", 
    "responseMessage": " Approved or completed successfully", 
    "responseCode": "00"
}
```

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
var data = JSON.stringify({
  "beneficiaryAccountName": "UGBO, CHARLES UMORE",
  "transactionAmount": "2000.45",
  "currencyCode": "NGN",
  "narration": "Testing",
  "sourceAccountName": "Nnamdi Adebayo Hamzat",
  "beneficiaryAccountNumber": "0045434120",
  "beneficiaryBank": "000013",
  "transactionReference": "20191119143854",
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

xhr.open("POST", "https://api-staging.providusbank.com/NIPFundTransfer");
xhr.setRequestHeader("Accept", "application/json");
xhr.setRequestHeader("Content-Type", "application/json");

xhr.send(data);
```

> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "transactionReference": "20191119143854",
    "sessionId": "999037230913163757005000082268", 
    "responseMessage": " Approved or completed successfully", 
    "responseCode": "00"
}
```

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
<?php
require_once 'HTTP/Request2.php';
$request = new HTTP_Request2();
$request->setUrl('https://api-staging.providusbank.com/NIPFundTransfer');
$request->setMethod(HTTP_Request2::METHOD_POST);
$request->setConfig(array(
  'follow_redirects' => TRUE
));
$request->setHeader(array(
  'Accept' => 'application/json',
  'Content-Type' => 'application/json'
));
$request->setBody('{\n"beneficiaryAccountName":"UGBO, CHARLES UMORE", "transactionAmount": "2000.45", "currencyCode":"NGN",\n"narration":"Testing",\n"sourceAccountName":"Nnamdi Adebayo Hamzat" , "beneficiaryAccountNumber":"0045434120", "beneficiaryBank":"000013", "transactionReference":"20191119143854", "userName":"test",\n"password":"test"\n}');
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
    "transactionReference": "20191119143854",
    "sessionId": "999037230913163757005000082268", 
    "responseMessage": " Approved or completed successfully", 
    "responseCode": "00"
}
```

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap whitespace-pre-wrap
var options = new RestClientOptions("https://api-staging.providusbank.com")
{
  MaxTimeout = -1,
};
var client = new RestClient(options);
var request = new RestRequest("/NIPFundTransfer", Method.Post);
request.AddHeader("Accept", "application/json");
request.AddHeader("Content-Type", "application/json");
var body = @"{" + "\n" +
@"""beneficiaryAccountName"":""UGBO, CHARLES UMORE"", ""transactionAmount"": ""2000.45"", ""currencyCode"":""NGN""," + "\n" +
@"""narration"":""Testing""," + "\n" +
@"""sourceAccountName"":""Nnamdi Adebayo Hamzat"" , ""beneficiaryAccountNumber"":""0045434120"", ""beneficiaryBank"":""000013"", ""transactionReference"":""20191119143854"", ""userName"":""test""," + "\n" +
@"""password"":""test""" + "\n" +
@"}";
request.AddStringBody(body, DataFormat.Json);
RestResponse response = await client.ExecuteAsync(request);
Console.WriteLine(response.Content);
```

> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "transactionReference": "20191119143854",
    "sessionId": "999037230913163757005000082268", 
    "responseMessage": " Approved or completed successfully", 
    "responseCode": "00"
}
```

Last updated 1 year ago