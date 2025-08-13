1. Transactions

# Get Transaction Status

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

Get the status of a transaction.

#### Test Base URL

https://api-staging.providusbank.com

#### Production Base URL

https://api.providusbank.com

#### HTTP Request

GET /account/bvn

## BVN Details.

`GET``https://api-staging.providusbank.com/v1/account/bvn`Get NIP Account.

#### Request Body

Username

string

Username of account owner

Password

string

Password of account owner

number

String

bvn number of account owner

### Sample Implementation

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap whitespace-pre-wrap
curl -x GET "https://api-demo.providusbank/account/NIP/banks"
  -H "Authorization: {{Authentication token}}"
  -H "Username: Username"
  -H "Password: Password"
inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "banks":[
        {"bankCode":"000014","bankName":"ACCESS BANK"},
        {"bankCode":"100013","bankName":"ACCESS MOBILE"},
        {"bankCode":"090133","bankName":"AL-BARAKAH MICROFINANCE BANK"},
        {"bankCode":"090116","bankName":"AMML MICROFINANCE BANK"},
        {"bankCode":"090001","bankName":"ASO SAVINGS"},
        {"bankCode":"090127","bankName":"BC KASH MICROFINANCE BANK"},
        {"bankCode":"090117","bankName":"BOCTRUST MICROFINANCE BANK LIMITED"},
        {"bankCode":"100005","bankName":"CELLULANT"},
        {"bankCode":"100015","bankName":"CHAMS MOBILE"},
        {"bankCode":"000009","bankName":"CITI BANK"},
        {"bankCode":"060001","bankName":"CORONATION BANK"},
        {"bankCode":"070006","bankName":"COVENANT MFB"},
        {"bankCode":"000005","bankName":"DIAMOND BANK"},
        {"bankCode":"100021","bankName":"EARTHOLEUM"},
        {"bankCode":"000010","bankName":"ECOBANK"},
        {"bankCode":"100008","bankName":"ECOBANK XPRESS ACCOUNT"},
        {"bankCode":"090114","bankName":"EMPIRE TRUST MICROFINANCE BANK"},
        {"bankCode":"000019","bankName":"ENTERPRISE BANK"},
        {"bankCode":"100006","bankName":"eTRANZACT"},
        {"bankCode":"060002","bankName":"FBN MERCHANT BANK"},
        {"bankCode":"100014","bankName":"FBN MOBILE"}
    ],
    "responseMessage":"SUCCESS",
    "responseCode":"00"}


> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "banks":[
        {"bankCode":"000014","bankName":"ACCESS BANK"},
        {"bankCode":"100013","bankName":"ACCESS MOBILE"},
        {"bankCode":"090133","bankName":"AL-BARAKAH MICROFINANCE BANK"},
        {"bankCode":"090116","bankName":"AMML MICROFINANCE BANK"},
        {"bankCode":"090001","bankName":"ASO SAVINGS"},
        {"bankCode":"090127","bankName":"BC KASH MICROFINANCE BANK"},
        {"bankCode":"090117","bankName":"BOCTRUST MICROFINANCE BANK LIMITED"},
        {"bankCode":"100005","bankName":"CELLULANT"},
        {"bankCode":"100015","bankName":"CHAMS MOBILE"},
        {"bankCode":"000009","bankName":"CITI BANK"},
        {"bankCode":"060001","bankName":"CORONATION BANK"},
        {"bankCode":"070006","bankName":"COVENANT MFB"},
        {"bankCode":"000005","bankName":"DIAMOND BANK"},
        {"bankCode":"100021","bankName":"EARTHOLEUM"},
        {"bankCode":"000010","bankName":"ECOBANK"},
        {"bankCode":"100008","bankName":"ECOBANK XPRESS ACCOUNT"},
        {"bankCode":"090114","bankName":"EMPIRE TRUST MICROFINANCE BANK"},
        {"bankCode":"000019","bankName":"ENTERPRISE BANK"},
        {"bankCode":"100006","bankName":"eTRANZACT"},
        {"bankCode":"060002","bankName":"FBN MERCHANT BANK"},
        {"bankCode":"100014","bankName":"FBN MOBILE"}
    ],
    "responseMessage":"SUCCESS",
    "responseCode":"00"}


> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "banks":[
        {"bankCode":"000014","bankName":"ACCESS BANK"},
        {"bankCode":"100013","bankName":"ACCESS MOBILE"},
        {"bankCode":"090133","bankName":"AL-BARAKAH MICROFINANCE BANK"},
        {"bankCode":"090116","bankName":"AMML MICROFINANCE BANK"},
        {"bankCode":"090001","bankName":"ASO SAVINGS"},
        {"bankCode":"090127","bankName":"BC KASH MICROFINANCE BANK"},
        {"bankCode":"090117","bankName":"BOCTRUST MICROFINANCE BANK LIMITED"},
        {"bankCode":"100005","bankName":"CELLULANT"},
        {"bankCode":"100015","bankName":"CHAMS MOBILE"},
        {"bankCode":"000009","bankName":"CITI BANK"},
        {"bankCode":"060001","bankName":"CORONATION BANK"},
        {"bankCode":"070006","bankName":"COVENANT MFB"},
        {"bankCode":"000005","bankName":"DIAMOND BANK"},
        {"bankCode":"100021","bankName":"EARTHOLEUM"},
        {"bankCode":"000010","bankName":"ECOBANK"},
        {"bankCode":"100008","bankName":"ECOBANK XPRESS ACCOUNT"},
        {"bankCode":"090114","bankName":"EMPIRE TRUST MICROFINANCE BANK"},
        {"bankCode":"000019","bankName":"ENTERPRISE BANK"},
        {"bankCode":"100006","bankName":"eTRANZACT"},
        {"bankCode":"060002","bankName":"FBN MERCHANT BANK"},
        {"bankCode":"100014","bankName":"FBN MOBILE"}
    ],
    "responseMessage":"SUCCESS",
    "responseCode":"00"}


> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "banks":[
        {"bankCode":"000014","bankName":"ACCESS BANK"},
        {"bankCode":"100013","bankName":"ACCESS MOBILE"},
        {"bankCode":"090133","bankName":"AL-BARAKAH MICROFINANCE BANK"},
        {"bankCode":"090116","bankName":"AMML MICROFINANCE BANK"},
        {"bankCode":"090001","bankName":"ASO SAVINGS"},
        {"bankCode":"090127","bankName":"BC KASH MICROFINANCE BANK"},
        {"bankCode":"090117","bankName":"BOCTRUST MICROFINANCE BANK LIMITED"},
        {"bankCode":"100005","bankName":"CELLULANT"},
        {"bankCode":"100015","bankName":"CHAMS MOBILE"},
        {"bankCode":"000009","bankName":"CITI BANK"},
        {"bankCode":"060001","bankName":"CORONATION BANK"},
        {"bankCode":"070006","bankName":"COVENANT MFB"},
        {"bankCode":"000005","bankName":"DIAMOND BANK"},
        {"bankCode":"100021","bankName":"EARTHOLEUM"},
        {"bankCode":"000010","bankName":"ECOBANK"},
        {"bankCode":"100008","bankName":"ECOBANK XPRESS ACCOUNT"},
        {"bankCode":"090114","bankName":"EMPIRE TRUST MICROFINANCE BANK"},
        {"bankCode":"000019","bankName":"ENTERPRISE BANK"},
        {"bankCode":"100006","bankName":"eTRANZACT"},
        {"bankCode":"060002","bankName":"FBN MERCHANT BANK"},
        {"bankCode":"100014","bankName":"FBN MOBILE"}
    ],
    "responseMessage":"SUCCESS",
    "responseCode":"00"}


> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "banks":[
        {"bankCode":"000014","bankName":"ACCESS BANK"},
        {"bankCode":"100013","bankName":"ACCESS MOBILE"},
        {"bankCode":"090133","bankName":"AL-BARAKAH MICROFINANCE BANK"},
        {"bankCode":"090116","bankName":"AMML MICROFINANCE BANK"},
        {"bankCode":"090001","bankName":"ASO SAVINGS"},
        {"bankCode":"090127","bankName":"BC KASH MICROFINANCE BANK"},
        {"bankCode":"090117","bankName":"BOCTRUST MICROFINANCE BANK LIMITED"},
        {"bankCode":"100005","bankName":"CELLULANT"},
        {"bankCode":"100015","bankName":"CHAMS MOBILE"},
        {"bankCode":"000009","bankName":"CITI BANK"},
        {"bankCode":"060001","bankName":"CORONATION BANK"},
        {"bankCode":"070006","bankName":"COVENANT MFB"},
        {"bankCode":"000005","bankName":"DIAMOND BANK"},
        {"bankCode":"100021","bankName":"EARTHOLEUM"},
        {"bankCode":"000010","bankName":"ECOBANK"},
        {"bankCode":"100008","bankName":"ECOBANK XPRESS ACCOUNT"},
        {"bankCode":"090114","bankName":"EMPIRE TRUST MICROFINANCE BANK"},
        {"bankCode":"000019","bankName":"ENTERPRISE BANK"},
        {"bankCode":"100006","bankName":"eTRANZACT"},
        {"bankCode":"060002","bankName":"FBN MERCHANT BANK"},
        {"bankCode":"100014","bankName":"FBN MOBILE"}
    ],
    "responseMessage":"SUCCESS",
    "responseCode":"00"}


> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
    "banks":[
        {"bankCode":"000014","bankName":"ACCESS BANK"},
        {"bankCode":"100013","bankName":"ACCESS MOBILE"},
        {"bankCode":"090133","bankName":"AL-BARAKAH MICROFINANCE BANK"},
        {"bankCode":"090116","bankName":"AMML MICROFINANCE BANK"},
        {"bankCode":"090001","bankName":"ASO SAVINGS"},
        {"bankCode":"090127","bankName":"BC KASH MICROFINANCE BANK"},
        {"bankCode":"090117","bankName":"BOCTRUST MICROFINANCE BANK LIMITED"},
        {"bankCode":"100005","bankName":"CELLULANT"},
        {"bankCode":"100015","bankName":"CHAMS MOBILE"},
        {"bankCode":"000009","bankName":"CITI BANK"},
        {"bankCode":"060001","bankName":"CORONATION BANK"},
        {"bankCode":"070006","bankName":"COVENANT MFB"},
        {"bankCode":"000005","bankName":"DIAMOND BANK"},
        {"bankCode":"100021","bankName":"EARTHOLEUM"},
        {"bankCode":"000010","bankName":"ECOBANK"},
        {"bankCode":"100008","bankName":"ECOBANK XPRESS ACCOUNT"},
        {"bankCode":"090114","bankName":"EMPIRE TRUST MICROFINANCE BANK"},
        {"bankCode":"000019","bankName":"ENTERPRISE BANK"},
        {"bankCode":"100006","bankName":"eTRANZACT"},
        {"bankCode":"060002","bankName":"FBN MERCHANT BANK"},
        {"bankCode":"100014","bankName":"FBN MOBILE"}
    ],
    "responseMessage":"SUCCESS",
    "responseCode":"00"}
```

Last updated 1 year ago