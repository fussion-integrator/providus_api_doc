# Get Providus Transaction Status

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

```
curl -x GET "https://api-staging.providusbank.com/payment/status?transactionReference=prov9988zzjzj11"
  -H "Authorization: {{Authentication token}}"
  -H "userName: userName"
  -H "password: password"
```

The above command returns JSON structured like this:

```
{
    "amount":"100.0",
    "creditAccount":"1700263070",
    "debitAccount":"5900085856", "transactionReference":"2345677777", "transactionDateTime":"2020-05-04 14:12:11.0", "currency":"NGN", "responseMessage":
    "OPERATION SUCCESSFUL",
    "responseCode":"00"
}
```

```
import requests
from requests.structures import CaseInsensitiveDict

url = "https://api-staging.providusbank.com/payment/NIP/status?transactionReference=prov9988zzjzj11"

headers = CaseInsensitiveDict()
headers["Authorization"] = "{{Authentication token}}"
headers["userName"] = "userName"
headers["password"] = "password"


resp = requests.get(url, headers=headers)

print(resp.status_code)
```

The above command returns JSON structured like this:

```
{
    "amount":"100.0",
    "creditAccount":"1700263070",
    "debitAccount":"5900085856", "transactionReference":"2345677777", "transactionDateTime":"2020-05-04 14:12:11.0", "currency":"NGN", "responseMessage":
    "OPERATION SUCCESSFUL",
    "responseCode":"00"
}
```

```
URL url = new URL("https://api-staging.providusbank.com/payment/NIP/status?transactionReference=prov9988zzjzj11");
HttpURLConnection http = (HttpURLConnection)url.openConnection();
http.setRequestProperty("Authorization", "{{Authentication token}}");
http.setRequestProperty("userName", "Username");
http.setRequestProperty("password", "Password");

System.out.println(http.getResponseCode() + " " + http.getResponseMessage());
http.disconnect();
```

The above command returns JSON structured like this:

```
{
    "amount":"100.0",
    "creditAccount":"1700263070",
    "debitAccount":"5900085856", "transactionReference":"2345677777", "transactionDateTime":"2020-05-04 14:12:11.0", "currency":"NGN", "responseMessage":
    "OPERATION SUCCESSFUL",
    "responseCode":"00"
}
```

```
var xhr = new XMLHttpRequest();
xhr.withCredentials = true;

xhr.addEventListener("readystatechange", function() {
  if(this.readyState === 4) {
    console.log(this.responseText);
  }
});
xhr.open("GET", "https://api-staging.providusbank.com/payment/NIP/status?transactionReference=prov9988zzjzj11");
xhr.setRequestHeader("Authorization", "{{Authentication token}}");
xhr.setRequestHeader("userName", "Username");
xhr.setRequestHeader("password", "Password");
xhr.send();
```

The above command returns JSON structured like this:

```
{
    "amount":"100.0",
    "creditAccount":"1700263070",
    "debitAccount":"5900085856", "transactionReference":"2345677777", "transactionDateTime":"2020-05-04 14:12:11.0", "currency":"NGN", "responseMessage":
    "OPERATION SUCCESSFUL",
    "responseCode":"00"
}
```

```
<?php
require_once 'HTTP/Request2.php';
$request = new HTTP_Request2();
$request->setUrl('https://api-staging.providusbank.com/payment/NIP/status?transactionReference=prov9988zzjzj11');
$request->setMethod(HTTP_Request2::METHOD_GET);
$request->setConfig(array(
  'follow_redirects' => TRUE
));
$request->setHeader(array(
  'Authorization' => '{{Authentication token}}',
  'userName' => 'Username',
  'password' => 'Password'
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
?>
```

The above command returns JSON structured like this:

```
{
    "amount":"100.0",
    "creditAccount":"1700263070",
    "debitAccount":"5900085856", "transactionReference":"2345677777", "transactionDateTime":"2020-05-04 14:12:11.0", "currency":"NGN", "responseMessage":
    "OPERATION SUCCESSFUL",
    "responseCode":"00"
}
```

```
var client = new RestClient("https://api-staging.providusbank.com/payment/NIP/status?transactionReference=prov9988zzjzj11");
client.Timeout = -1;
var request = new RestRequest(Method.GET);
request.AddHeader("Authorization", "{{Authentication token}}");
request.AddHeader("userName", "Username");
request.AddHeader("password", "Password");
IRestResponse response = client.Execute(request);
Console.WriteLine(response.Content);
```

The above command returns JSON structured like this:

```
{
    "amount":"100.0",
    "creditAccount":"1700263070",
    "debitAccount":"5900085856", "transactionReference":"2345677777", "transactionDateTime":"2020-05-04 14:12:11.0", "currency":"NGN", "responseMessage":
    "OPERATION SUCCESSFUL",
    "responseCode":"00"
}
```

Last updated 1 year ago