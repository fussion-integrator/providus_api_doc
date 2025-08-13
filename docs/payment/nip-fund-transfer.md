1. Payment

# NIP Fund Transfer

## Code Examples

<CodeTabs tabs={[
  { language: "curl", code: `curl -X GET "https://api-staging.providusbank.com" \
  -H "Authorization: Bearer YOUR_API_KEY" \
  -H "Content-Type: application/json"` },
  { language: "javascript", code: `const response = await fetch('https://api-staging.providusbank.com', {
  method: 'GET',
  headers: {
    'Authorization': 'Bearer YOUR_API_KEY',
    'Content-Type': 'application/json'
  }
});

const data = await response.json();
console.log(data);` },
  { language: "python", code: `import requests

url = "https://api-staging.providusbank.com"
headers = {
    "Authorization": "Bearer YOUR_API_KEY",
    "Content-Type": "application/json"
}

response = requests.get(url, headers=headers)
print(response.json())` },
  { language: "java", code: `HttpClient client = HttpClient.newHttpClient();
HttpRequest request = HttpRequest.newBuilder()
    .uri(URI.create("https://api-staging.providusbank.com"))
    .header("Authorization", "Bearer YOUR_API_KEY")
    .header("Content-Type", "application/json")
    .GET(HttpRequest.BodyPublishers.noBody())
    .build();

HttpResponse<String> response = client.send(request, HttpResponse.BodyHandlers.ofString());` },
  { language: "php", code: `<?php
$url = "https://api-staging.providusbank.com";
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
?>` },
  { language: "csharp", code: `var client = new HttpClient();
client.DefaultRequestHeaders.Add("Authorization", "Bearer YOUR_API_KEY");

var response = await client.GetAsync("https://api-staging.providusbank.com");

var responseContent = await response.Content.ReadAsStringAsync();` }
]} />

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
inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap whitespace-pre-wrap
curl --location 'https://api-staging.providusbank.com/NIPFundTransfer' \
--header 'Accept: application/json' \
--header 'Content-Type: application/json' \
--data '{
"beneficiaryAccountName":"UGBO, CHARLES UMORE", "transactionAmount": "2000.45", "currencyCode":"NGN",
"narration":"Testing",
"sourceAccountName":"Nnamdi Adebayo Hamzat" , "beneficiaryAccountNumber":"0045434120", "beneficiaryBank":"000013", "transactionReference":"20191119143854", "userName":"test",
"password":"test"
}'

inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "transactionReference": "20191119143854",
    "sessionId": "999037230913163757005000082268", 
    "responseMessage": " Approved or completed successfully", 
    "responseCode": "00"
}


> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "transactionReference": "20191119143854",
    "sessionId": "999037230913163757005000082268", 
    "responseMessage": " Approved or completed successfully", 
    "responseCode": "00"
}


> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "transactionReference": "20191119143854",
    "sessionId": "999037230913163757005000082268", 
    "responseMessage": " Approved or completed successfully", 
    "responseCode": "00"
}


> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "transactionReference": "20191119143854",
    "sessionId": "999037230913163757005000082268", 
    "responseMessage": " Approved or completed successfully", 
    "responseCode": "00"
}


> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "transactionReference": "20191119143854",
    "sessionId": "999037230913163757005000082268", 
    "responseMessage": " Approved or completed successfully", 
    "responseCode": "00"
}


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