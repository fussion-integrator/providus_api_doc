1. Payment

# Get Providus Account

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

Get a Providus bank user account.

#### Test Base URL

https://api-staging.providusbank.com

#### Production Base URL

https://api.providusbank.com

#### HTTP Request

POST /GetProvidusAccount

## Providus Account.

`POST``https://api-staging.providusbank.com/v1/GetProvidusAccount`Get Providus Account.

#### Request Body

Username

string

Username of account owner

Password

string

Password of account owner

account_number

String

account number for the account

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
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
inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap whitespace-pre-wrap
curl --location 'https://api-staging.providusbank.com/GetProvidusAccount' \
--header 'Accept: application/json' \
--header 'Content-Type: application/json' \
--data '{
    "accountNumber": "1700263070",
    "userName" : "test",
    "password" : "test" 
}'
inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
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


> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
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


> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
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


> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
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


> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
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


> The above command returns JSON structured like this:

The above command returns JSON structured like this:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
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

Last updated 1 year ago