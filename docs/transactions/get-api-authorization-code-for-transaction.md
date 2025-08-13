1. Transactions

# Get API authorization code for transaction

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

Get an authorization code for the Transaction API.

#### Test Base URL

https://api-staging.providusbank.com

#### Production Base URL

https://api.providusbank.com

#### HTTP Request

`GET /transaction/oauth/authorize/`## Authorization Code.

`GET``https://api-staging.providusbank.com/v1 /account/NIP`Get API authorization code for transaction.

#### Headers

Content-Type

String

Request content type ( application/x-www-form-urlencoded )

#### Request Body

response_type*

String

`code`client_id

String

The OAuth client id

redirect_uri

string

The OAuth client redirect URI ( must be URL encoded )

### Sample Implementation

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap whitespace-pre-wrap
curl --location --request POST 'https://mgw-staging.providusbank.com/transaction/oauth/authorize/' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--header 'Authorization: Basic NGNlMjQ5YmIzMTFmNGFlZWFmYzNlNDA2OTBjNzc4ZGM6WkRjMVlUbGxNRGd0WVdKa1lpMDBOalJqTFdKak5qUXROV0poTVRnMU16aGpZV1Zt' \
--data-urlencode 'grant_type=authorization_code' \
--data-urlencode 'client_id=091ddd8ca61c488aafcd078f2989eee0' \
--data-urlencode 'code=ZDc1YTllMDgtYWJkYi00NjRjLWJjNjQtNWJhMTg1MzhjYWVm' \
--data-urlencode 'redirect_uri=http%3A%2F%2F192.81.212.28%3A4003%2Foauth'
inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
import requests
from requests.structures import CaseInsensitiveDict
url = "https://api-staging.providusbank.com/account/NIP?account_number=3041004406&bank_code=57"
headers = CaseInsensitiveDict()
headers["Authorization"] = "{{Authentication token}}"
headers["Username"] = "Username"
headers["Password"] = "Password"
resp = requests.get(url, headers=headers)
print(resp.status_code)
inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
URL url = new URL("https://api-staging.providusbank.com/account/NIP?account_number=3041004406&bank_code=57");
HttpURLConnection http = (HttpURLConnection)url.openConnection();
http.setRequestProperty("Authorization", "{{Authentication token}}");
http.setRequestProperty("Username", "Username");
http.setRequestProperty("Password", "Password");
System.out.println(http.getResponseCode() + " " + http.getResponseMessage());
http.disconnect();
inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
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
inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
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
inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
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

The above command returns JSON structured like this:

Last updated 1 year ago