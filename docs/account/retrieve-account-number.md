1. Account

# Retrieve Account Number

Retrieve an Account number.

#### Test Base URL

https://api-staging.providusbank.com

#### Production Base URL

https://api.providusbank.com

#### HTTP Request

GET /account/account

## Providus Account.

`GET``https://api-staging.providusbank.com/v1/account`Get NIP Account.

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
```

### Sample Implementation

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap whitespace-pre-wrap
curl -x GET "https://api-demo.providusbank/account/?account_number=00017000" 
  -H "Authorization: {{Authentication token}}"
  -H "Username: Username"
  -H "Password: Password"
```

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

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
import requests
from requests.structures import CaseInsensitiveDict

url = "https://api-demo.providusbank/account/?account_number=023687000"

headers = CaseInsensitiveDict()
headers["Authorization"] = "{{Authentication token}}"
headers["Username"] = "Username"
headers["Password"] = "Password"


resp = requests.get(url, headers=headers)

print(resp.status_code)
```

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

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
URL url = new URL("https://api-demo.providusbank/account/?account_number=02030870010017000");
HttpURLConnection http = (HttpURLConnection)url.openConnection();
http.setRequestProperty("Authorization", "{{Authentication token}}");
http.setRequestProperty("Username", "Username");
http.setRequestProperty("Password", "Password");

System.out.println(http.getResponseCode() + " " + http.getResponseMessage());
http.disconnect();
```

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

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
var xhr = new XMLHttpRequest();
xhr.withCredentials = true;

xhr.addEventListener("readystatechange", function() {
  if(this.readyState === 4) {
    console.log(this.responseText);
  }
});
xhr.open("GET", "https://api-staging.providusbank.com/account/?account_number=0203006780");
xhr.setRequestHeader("Authorization", "{{Authentication token}}");
xhr.setRequestHeader("Username", "Username");
xhr.setRequestHeader("Password", "Password");
xhr.send();
```

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

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
<?php
require_once 'HTTP/Request2.php';
$request = new HTTP_Request2();
$request->setUrl('https://api-staging.providusbank.com/account/?account_number=0203006788');
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

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
var client = new RestClient("https://api-staging.providusbank.com/account/?account_number=020300678870010017000");
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

Last updated 10 days ago