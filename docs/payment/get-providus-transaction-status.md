1. Payment

# Get Providus Transaction Status

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

POST  /payment/status

## NIP Bank.

`POST``https://api-staging.providusbank.com/v1/account/NIP/banks`Get Providus transactions by status.

#### Request Body

userName

String

Username of account owner

password

String

Password of account owner

transactionReference

String

Reference to the transaction

### Sample Implementation

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap whitespace-pre-wrap
curl -x GET "https://api-staging.providusbank.com/payment/status?transactionReference=prov9988zzjzj11"
  -H "Authorization: {{Authentication token}}"
  -H "userName: userName"
  -H "password: password"
inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "amount":"100.0",
    "creditAccount":"1700263070",
    "debitAccount":"5900085856", "transactionReference":"2345677777", "transactionDateTime":"2020-05-04 14:12:11.0", "currency":"NGN", "responseMessage":
    "OPERATION SUCCESSFUL",
    "responseCode":"00"
}


> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "amount":"100.0",
    "creditAccount":"1700263070",
    "debitAccount":"5900085856", "transactionReference":"2345677777", "transactionDateTime":"2020-05-04 14:12:11.0", "currency":"NGN", "responseMessage":
    "OPERATION SUCCESSFUL",
    "responseCode":"00"
}


> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "amount":"100.0",
    "creditAccount":"1700263070",
    "debitAccount":"5900085856", "transactionReference":"2345677777", "transactionDateTime":"2020-05-04 14:12:11.0", "currency":"NGN", "responseMessage":
    "OPERATION SUCCESSFUL",
    "responseCode":"00"
}


> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "amount":"100.0",
    "creditAccount":"1700263070",
    "debitAccount":"5900085856", "transactionReference":"2345677777", "transactionDateTime":"2020-05-04 14:12:11.0", "currency":"NGN", "responseMessage":
    "OPERATION SUCCESSFUL",
    "responseCode":"00"
}


> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "amount":"100.0",
    "creditAccount":"1700263070",
    "debitAccount":"5900085856", "transactionReference":"2345677777", "transactionDateTime":"2020-05-04 14:12:11.0", "currency":"NGN", "responseMessage":
    "OPERATION SUCCESSFUL",
    "responseCode":"00"
}


> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "amount":"100.0",
    "creditAccount":"1700263070",
    "debitAccount":"5900085856", "transactionReference":"2345677777", "transactionDateTime":"2020-05-04 14:12:11.0", "currency":"NGN", "responseMessage":
    "OPERATION SUCCESSFUL",
    "responseCode":"00"
}
```

Last updated 1 year ago