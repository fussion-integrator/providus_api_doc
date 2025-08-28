# Code Samples

## 

[](#api-code-samples-for-customer-and-wallet-management)

API Code Samples for Customer and Wallet Management

Below are code samples for each endpoint in the Customer and Wallet Management API, implemented in cURL, Python, Java, JavaScript, PHP, and C#. Each sample corresponds to the respective endpoint for interacting with the API.

* * *

### 

[](#customer-management)

Customer Management

#### 

[](#get-all-customers)

Get All Customers

*   **cURL**:
    

Copy

```
curl --request GET \
  --url '{{base-url}}/customer?page=1' \
  --header 'X-Access-Token: {{access-token}}' \
  --header 'X-Refresh-Token: {{refresh-token}}'
```

*   **Python**:
    

Copy

```
import requests

headers = {
    'X-Access-Token': '{{access-token}}',
    'X-Refresh-Token': '{{refresh-token}}'
}

response = requests.get('{{base-url}}/customer?page=1', headers=headers)
if response.status_code == 200:
    print(response.json())
else:
    print(response.reason)
```

*   **Java**:
    

Copy

```
import java.net.HttpURLConnection;
import java.net.URL;
import java.io.BufferedReader;
import java.io.InputStreamReader;

public class Main {
    public static void main(String[] args) throws Exception {
        URL url = new URL("{{base-url}}/customer?page=1");
        HttpURLConnection conn = (HttpURLConnection) url.openConnection();
        conn.setRequestMethod("GET");
        conn.setRequestProperty("X-Access-Token", "{{access-token}}");
        conn.setRequestProperty("X-Refresh-Token", "{{refresh-token}}");

        int responseCode = conn.getResponseCode();
        if (responseCode == 200) {
            BufferedReader in = new BufferedReader(new InputStreamReader(conn.getInputStream()));
            String inputLine;
            StringBuilder response = new StringBuilder();
            while ((inputLine = in.readLine()) != null) {
                response.append(inputLine);
            }
            in.close();
            System.out.println(response.toString());
        } else {
            System.out.println(conn.getResponseMessage());
        }
    }
}
```

*   **JavaScript**:
    

Copy

```
const headers = {
    'X-Access-Token': '{{access-token}}',
    'X-Refresh-Token': '{{refresh-token}}'
};

fetch('{{base-url}}/customer?page=1', {
    method: 'GET',
    headers: headers
})
.then(response => {
    if (response.ok) {
        return response.json();
    }
    throw new Error(response.statusText);
})
.then(data => console.log(data))
.catch(error => console.error(error));
```

*   **PHP**:
    

Copy

```
<?php
$ch = curl_init();

curl_setopt($ch, CURLOPT_URL, "{{base-url}}/customer?page=1");
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_HTTPHEADER, [
    'X-Access-Token: {{access-token}}',
    'X-Refresh-Token: {{refresh-token}}'
]);

$response = curl_exec($ch);
$httpCode = curl_getinfo($ch, CURLINFO_HTTP_CODE);

if ($httpCode == 200) {
    echo $response;
} else {
    echo curl_error($ch);
}

curl_close($ch);
?>
```

*   **C#**:
    

Copy

```
using System;
using System.Net.Http;
using System.Threading.Tasks;

class Program
{
    static async Task Main(string[] args)
    {
        using (var client = new HttpClient())
        {
            client.DefaultRequestHeaders.Add("X-Access-Token", "{{access-token}}");
            client.DefaultRequestHeaders.Add("X-Refresh-Token", "{{refresh-token}}");

            var response = await client.GetAsync("{{base-url}}/customer?page=1");
            if (response.IsSuccessStatusCode)
            {
                var content = await response.Content.ReadAsStringAsync();
                Console.WriteLine(content);
            }
            else
            {
                Console.WriteLine(response.ReasonPhrase);
            }
        }
    }
}
```

#### 

[](#get-customer-details)

Get Customer Details

*   **cURL**:
    

Copy

```
curl --request GET \
  --url '{{base-url}}/customer/1149d065-c5c9-4382-aec6-323090f31d9d' \
  --header 'X-Access-Token: {{access-token}}' \
  --header 'X-Refresh-Token: {{refresh-token}}'
```

*   **Python**:
    

Copy

```
import requests

headers = {
    'X-Access-Token': '{{access-token}}',
    'X-Refresh-Token': '{{refresh-token}}'
}

response = requests.get('{{base-url}}/customer/1149d065-c5c9-4382-aec6-323090f31d9d', headers=headers)
if response.status_code == 200:
    print(response.json())
else:
    print(response.reason)
```

*   **Java**:
    

Copy

```
import java.net.HttpURLConnection;
import java.net.URL;
import java.io.BufferedReader;
import java.io.InputStreamReader;

public class Main {
    public static void main(String[] args) throws Exception {
        URL url = new URL("{{base-url}}/customer/1149d065-c5c9-4382-aec6-323090f31d9d");
        HttpURLConnection conn = (HttpURLConnection) url.openConnection();
        conn.setRequestMethod("GET");
        conn.setRequestProperty("X-Access-Token", "{{access-token}}");
        conn.setRequestProperty("X-Refresh-Token", "{{refresh-token}}");

        int responseCode = conn.getResponseCode();
        if (responseCode == 200) {
            BufferedReader in = new BufferedReader(new InputStreamReader(conn.getInputStream()));
            String inputLine;
            StringBuilder response = new StringBuilder();
            while ((inputLine = in.readLine()) != null) {
                response.append(inputLine);
            }
            in.close();
            System.out.println(response.toString());
        } else {
            System.out.println(conn.getResponseMessage());
        }
    }
}
```

*   **JavaScript**:
    

Copy

```
const headers = {
    'X-Access-Token': '{{access-token}}',
    'X-Refresh-Token': '{{refresh-token}}'
};

fetch('{{base-url}}/customer/1149d065-c5c9-4382-aec6-323090f31d9d', {
    method: 'GET',
    headers: headers
})
.then(response => {
    if (response.ok) {
        return response.json();
    }
    throw new Error(response.statusText);
})
.then(data => console.log(data))
.catch(error => console.error(error));
```

*   **PHP**:
    

Copy

```
<?php
$ch = curl_init();

curl_setopt($ch, CURLOPT_URL, "{{base-url}}/customer/1149d065-c5c9-4382-aec6-323090f31d9d");
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_HTTPHEADER, [
    'X-Access-Token: {{access-token}}',
    'X-Refresh-Token: {{refresh-token}}'
]);

$response = curl_exec($ch);
$httpCode = curl_getinfo($ch, CURLINFO_HTTP_CODE);

if ($httpCode == 200) {
    echo $response;
} else {
    echo curl_error($ch);
}

curl_close($ch);
?>
```

*   **C#**:
    

Copy

```
using System;
using System.Net.Http;
using System.Threading.Tasks;

class Program
{
    static async Task Main(string[] args)
    {
        using (var client = new HttpClient())
        {
            client.DefaultRequestHeaders.Add("X-Access-Token", "{{access-token}}");
            client.DefaultRequestHeaders.Add("X-Refresh-Token", "{{refresh-token}}");

            var response = await client.GetAsync("{{base-url}}/customer/1149d065-c5c9-4382-aec6-323090f31d9d");
            if (response.IsSuccessStatusCode)
            {
                var content = await response.Content.ReadAsStringAsync();
                Console.WriteLine(content);
            }
            else
            {
                Console.WriteLine(response.ReasonPhrase);
            }
        }
    }
}
```

#### 

[](#find-customer-by-phone-number)

Find Customer by Phone Number

*   **cURL**:
    

Copy

```
curl --request GET \
  --url '{{base-url}}/customer/phone?phoneNumber=08030223346' \
  --header 'X-Access-Token: {{access-token}}' \
  --header 'X-Refresh-Token: {{refresh-token}}'
```

*   **Python**:
    

Copy

```
import requests

headers = {
    'X-Access-Token': '{{access-token}}',
    'X-Refresh-Token': '{{refresh-token}}'
}

response = requests.get('{{base-url}}/customer/phone?phoneNumber=08030223346', headers=headers)
if response.status_code == 200:
    print(response.json())
else:
    print(response.reason)
```

*   **Java**:
    

Copy

```
import java.net.HttpURLConnection;
import java.net.URL;
import java.io.BufferedReader;
import java.io.InputStreamReader;

public class Main {
    public static void main(String[] args) throws Exception {
        URL url = new URL("{{base-url}}/customer/phone?phoneNumber=08030223346");
        HttpURLConnection conn = (HttpURLConnection) url.openConnection();
        conn.setRequestMethod("GET");
        conn.setRequestProperty("X-Access-Token", "{{access-token}}");
        conn.setRequestProperty("X-Refresh-Token", "{{refresh-token}}");

        int responseCode = conn.getResponseCode();
        if (responseCode == 200) {
            BufferedReader in = new BufferedReader(new InputStreamReader(conn.getInputStream()));
            String inputLine;
            StringBuilder response = new StringBuilder();
            while ((inputLine = in.readLine()) != null) {
                response.append(inputLine);
            }
            in.close();
            System.out.println(response.toString());
        } else {
            System.out.println(conn.getResponseMessage());
        }
    }
}
```

*   **JavaScript**:
    

Copy

```
const headers = {
    'X-Access-Token': '{{access-token}}',
    'X-Refresh-Token': '{{refresh-token}}'
};

fetch('{{base-url}}/customer/phone?phoneNumber=08030223346', {
    method: 'GET',
    headers: headers
})
.then(response => {
    if (response.ok) {
        return response.json();
    }
    throw new Error(response.statusText);
})
.then(data => console.log(data))
.catch(error => console.error(error));
```

*   **PHP**:
    

Copy

```
<?php
$ch = curl_init();

curl_setopt($ch, CURLOPT_URL, "{{base-url}}/customer/phone?phoneNumber=08030223346");
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_HTTPHEADER, [
    'X-Access-Token: {{access-token}}',
    'X-Refresh-Token: {{refresh-token}}'
]);

$response = curl_exec($ch);
$httpCode = curl_getinfo($ch, CURLINFO_HTTP_CODE);

if ($httpCode == 200) {
    echo $response;
} else {
    echo curl_error($ch);
}

curl_close($ch);
?>
```

*   **C#**:
    

Copy

```
using System;
using System.Net.Http;
using System.Threading.Tasks;

class Program
{
    static async Task Main(string[] args)
    {
        using (var client = new HttpClient())
        {
            client.DefaultRequestHeaders.Add("X-Access-Token", "{{access-token}}");
            client.DefaultRequestHeaders.Add("X-Refresh-Token", "{{refresh-token}}");

            var response = await client.GetAsync("{{base-url}}/customer/phone?phoneNumber=08030223346");
            if (response.IsSuccessStatusCode)
            {
                var content = await response.Content.ReadAsStringAsync();
                Console.WriteLine(content);
            }
            else
            {
                Console.WriteLine(response.ReasonPhrase);
            }
        }
    }
}
```

#### 

[](#update-customer-profile)

Update Customer Profile

*   **cURL**:
    

Copy

```
curl --request PUT \
  --url '{{base-url}}/customer/49d4ea6d-d3dc-490c-800d-7c50b89cf8ff' \
  --header 'Content-Type: application/json' \
  --header 'X-Access-Token: {{access-token}}' \
  --header 'X-Refresh-Token: {{refresh-token}}' \
  --data '{
    "firstName": "Updated"
}'
```

*   **Python**:
    

Copy

```
import requests

headers = {
    'X-Access-Token': '{{access-token}}',
    'X-Refresh-Token': '{{refresh-token}}',
    'Content-Type': 'application/json'
}

data = {
    "firstName": "Updated"
}

response = requests.put('{{base-url}}/customer/49d4ea6d-d3dc-490c-800d-7c50b89cf8ff', headers=headers, json=data)
if response.status_code == 200:
    print(response.json())
else:
    print(response.reason)
```

*   **Java**:
    

Copy

```
import java.net.HttpURLConnection;
import java.net.URL;
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.io.OutputStream;

public class Main {
    public static void main(String[] args) throws Exception {
        URL url = new URL("{{base-url}}/customer/49d4ea6d-d3dc-490c-800d-7c50b89cf8ff");
        HttpURLConnection conn = (HttpURLConnection) url.openConnection();
        conn.setRequestMethod("PUT");
        conn.setRequestProperty("X-Access-Token", "{{access-token}}");
        conn.setRequestProperty("X-Refresh-Token", "{{refresh-token}}");
        conn.setRequestProperty("Content-Type", "application/json");
        conn.setDoOutput(true);

        String jsonInputString = "{\"firstName\": \"Updated\"}";
        try (OutputStream os = conn.getOutputStream()) {
            byte[] input = jsonInputString.getBytes("utf-8");
            os.write(input, 0, input.length);
        }

        int responseCode = conn.getResponseCode();
        if (responseCode == 200) {
            BufferedReader in = new BufferedReader(new InputStreamReader(conn.getInputStream()));
            String inputLine;
            StringBuilder response = new StringBuilder();
            while ((inputLine = in.readLine()) != null) {
                response.append(inputLine);
            }
            in.close();
            System.out.println(response.toString());
        } else {
            System.out.println(conn.getResponseMessage());
        }
    }
}
```

*   **JavaScript**:
    

Copy

```
const headers = {
    'X-Access-Token': '{{access-token}}',
    'X-Refresh-Token': '{{refresh-token}}',
    'Content-Type': 'application/json'
};

fetch('{{base-url}}/customer/49d4ea6d-d3dc-490c-800d-7c50b89cf8ff', {
    method: 'PUT',
    headers: headers,
    body: JSON.stringify({
        firstName: "Updated"
    })
})
.then(response => {
    if (response.ok) {
        return response.json();
    }
    throw new Error(response.statusText);
})
.then(data => console.log(data))
.catch(error => console.error(error));
```

*   **PHP**:
    

Copy

```
<?php
$ch = curl_init();

curl_setopt($ch, CURLOPT_URL, "{{base-url}}/customer/49d4ea6d-d3dc-490c-800d-7c50b89cf8ff");
curl_setopt($ch, CURLOPT_CUSTOMREQUEST, "PUT");
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_HTTPHEADER, [
    'X-Access-Token: {{access-token}}',
    'X-Refresh-Token: {{refresh-token}}',
    'Content-Type: application/json'
]);
curl_setopt($ch, CURLOPT_POSTFIELDS, '{"firstName": "Updated"}');

$response = curl_exec($ch);
$httpCode = curl_getinfo($ch, CURLINFO_HTTP_CODE);

if ($httpCode == 200) {
    echo $response;
} else {
    echo curl_error($ch);
}

curl_close($ch);
?>
```

*   **C#**:
    

Copy

```
using System;
using System.Net.Http;
using System.Text;
using System.Threading.Tasks;

class Program
{
    static async Task Main(string[] args)
    {
        using (var client = new HttpClient())
        {
            client.DefaultRequestHeaders.Add("X-Access-Token", "{{access-token}}");
            client.DefaultRequestHeaders.Add("X-Refresh-Token", "{{refresh-token}}");

            var content = new StringContent(
                "{\"firstName\": \"Updated\"}",
                Encoding.UTF8,
                "application/json"
            );

            var response = await client.PutAsync("{{base-url}}/customer/49d4ea6d-d3dc-490c-800d-7c50b89cf8ff", content);
            if (response.IsSuccessStatusCode)
            {
                var responseContent = await response.Content.ReadAsStringAsync();
                Console.WriteLine(responseContent);
            }
            else
            {
                Console.WriteLine(response.ReasonPhrase);
            }
        }
    }
}
```

### 

[](#wallet-management)

Wallet Management

#### 

[](#create-customer-wallet)

Create Customer Wallet

*   **cURL**:
    

Copy

```
curl --request POST \
  --url '{{base-url}}/wallet' \
  --header 'Content-Type: application/json' \
  --header 'X-Access-Token: {{access-token}}' \
  --header 'X-Refresh-Token: {{refresh-token}}' \
  --data '{
    "bvn": "22181029312",
    "firstName": "Ridwan",
    "lastName": "Adekunle",
    "dateOfBirth": "1992-05-16",
    "phoneNumber": "08020245356",
    "address": "No 10, Adewale Ajasin University",
    "metadata": {
        "even-more": "Other data",
        "additional-data": "some more data"
    }
}'
```

*   **Python**:
    

Copy

```
import requests

headers = {
    'X-Access-Token': '{{access-token}}',
    'X-Refresh-Token': '{{refresh-token}}',
    'Content-Type': 'application/json'
}

data = {
    "bvn": "22181029312",
    "firstName": "Ridwan",
    "lastName": "Adekunle",
    "dateOfBirth": "1992-05-16",
    "phoneNumber": "08020245356",
    "address": "No 10, Adewale Ajasin University",
    "metadata": {
        "even-more": "Other data",
        "additional-data": "some more data"
    }
}

response = requests.post('{{base-url}}/wallet', headers=headers, json=data)
if response.status_code == 200:
    print(response.json())
else:
    print(response.reason)
```

*   **Java**:
    

Copy

```
import java.net.HttpURLConnection;
import java.net.URL;
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.io.OutputStream;

public class Main {
    public static void main(String[] args) throws Exception {
        URL url = new URL("{{base-url}}/wallet");
        HttpURLConnection conn = (HttpURLConnection) url.openConnection();
        conn.setRequestMethod("POST");
        conn.setRequestProperty("X-Access-Token", "{{access-token}}");
        conn.setRequestProperty("X-Refresh-Token", "{{refresh-token}}");
        conn.setRequestProperty("Content-Type", "application/json");
        conn.setDoOutput(true);

        String jsonInputString = "{\"bvn\": \"22181029312\", \"firstName\": \"Ridwan\", \"lastName\": \"Adekunle\", \"dateOfBirth\": \"1992-05-16\", \"phoneNumber\": \"08020245356\", \"address\": \"No 10, Adewale Ajasin University\", \"metadata\": {\"even-more\": \"Other data\", \"additional-data\": \"some more data\"}}";
        try (OutputStream os = conn.getOutputStream()) {
            byte[] input = jsonInputString.getBytes("utf-8");
            os.write(input, 0, input.length);
        }

        int responseCode = conn.getResponseCode();
        if (responseCode == 200) {
            BufferedReader in = new BufferedReader(new InputStreamReader(conn.getInputStream()));
            String inputLine;
            StringBuilder response = new StringBuilder();
            while ((inputLine = in.readLine()) != null) {
                response.append(inputLine);
            }
            in.close();
            System.out.println(response.toString());
        } else {
            System.out.println(conn.getResponseMessage());
        }
    }
}
```

*   **JavaScript**:
    

Copy

```
const headers = {
    'X-Access-Token': '{{access-token}}',
    'X-Refresh-Token': '{{refresh-token}}',
    'Content-Type': 'application/json'
};

fetch('{{base-url}}/wallet', {
    method: 'POST',
    headers: headers,
    body: JSON.stringify({
        bvn: "22181029312",
        firstName: "Ridwan",
        lastName: "Adekunle",
        dateOfBirth: "1992-05-16",
        phoneNumber: "08020245356",
        address: "No 10, Adewale Ajasin University",
        metadata: {
            "even-more": "Other data",
            "additional-data": "some more data"
        }
    })
})
.then(response => {
    if (response.ok) {
        return response.json();
    }
    throw new Error(response.statusText);
})
.then(data => console.log(data))
.catch(error => console.error(error));
```

*   **PHP**:
    

Copy

```
<?php
$ch = curl_init();

curl_setopt($ch, CURLOPT_URL, "{{base-url}}/wallet");
curl_setopt($ch, CURLOPT_POST, true);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_HTTPHEADER, [
    'X-Access-Token: {{access-token}}',
    'X-Refresh-Token: {{refresh-token}}',
    'Content-Type: application/json'
]);
curl_setopt($ch, CURLOPT_POSTFIELDS, '{"bvn": "22181029312", "firstName": "Ridwan", "lastName": "Adekunle", "dateOfBirth": "1992-05-16", "phoneNumber": "08020245356", "address": "No 10, Adewale Ajasin University", "metadata": {"even-more": "Other data", "additional-data": "some more data"}}');

$response = curl_exec($ch);
$httpCode = curl_getinfo($ch, CURLINFO_HTTP_CODE);

if ($httpCode == 200) {
    echo $response;
} else {
    echo curl_error($ch);
}

curl_close($ch);
?>
```

*   **C#**:
    

Copy

```
using System;
using System.Net.Http;
using System.Text;
using System.Threading.Tasks;

class Program
{
    static async Task Main(string[] args)
    {
        using (var client = new HttpClient())
        {
            client.DefaultRequestHeaders.Add("X-Access-Token", "{{access-token}}");
            client.DefaultRequestHeaders.Add("X-Refresh-Token", "{{refresh-token}}");

            var content = new StringContent(
                "{\"bvn\": \"22181029312\", \"firstName\": \"Ridwan\", \"lastName\": \"Adekunle\", \"dateOfBirth\": \"1992-05-16\", \"phoneNumber\": \"08020245356\", \"address\": \"No 10, Adewale Ajasin University\", \"metadata\": {\"even-more\": \"Other data\", \"additional-data\": \"some more data\"}}",
                Encoding.UTF8,
                "application/json"
            );

            var response = await client.PostAsync("{{base-url}}/wallet", content);
            if (response.IsSuccessStatusCode)
            {
                var responseContent = await response.Content.ReadAsStringAsync();
                Console.WriteLine(responseContent);
            }
            else
            {
                Console.WriteLine(response.ReasonPhrase);
            }
        }
    }
}
```

#### 

[](#get-all-wallets)

Get All Wallets

*   **cURL**:
    

Copy

```
curl --request GET \
  --url '{{base-url}}/wallet' \
  --header 'X-Access-Token: {{access-token}}' \
  --header 'X-Refresh-Token: {{refresh-token}}'
```

*   **Python**:
    

Copy

```
import requests

headers = {
    'X-Access-Token': '{{access-token}}',
    'X-Refresh-Token': '{{refresh-token}}'
}

response = requests.get('{{base-url}}/wallet', headers=headers)
if response.status_code == 200:
    print(response.json())
else:
    print(response.reason)
```

*   **Java**:
    

Copy

```
import java.net.HttpURLConnection;
import java.net.URL;
import java.io.BufferedReader;
import java.io.InputStreamReader;

public class Main {
    public static void main(String[] args) throws Exception {
        URL url = new URL("{{base-url}}/wallet");
        HttpURLConnection conn = (HttpURLConnection) url.openConnection();
        conn.setRequestMethod("GET");
        conn.setRequestProperty("X-Access-Token", "{{access-token}}");
        conn.setRequestProperty("X-Refresh-Token", "{{refresh-token}}");

        int responseCode = conn.getResponseCode();
        if (responseCode == 200) {
            BufferedReader in = new BufferedReader(new InputStreamReader(conn.getInputStream()));
            String inputLine;
            StringBuilder response = new StringBuilder();
            while ((inputLine = in.readLine()) != null) {
                response.append(inputLine);
            }
            in.close();
            System.out.println(response.toString());
        } else {
            System.out.println(conn.getResponseMessage());
        }
    }
}
```

*   **JavaScript**:
    

Copy

```
const headers = {
    'X-Access-Token': '{{access-token}}',
    'X-Refresh-Token': '{{refresh-token}}'
};

fetch('{{base-url}}/wallet', {
    method: 'GET',
    headers: headers
})
.then(response => {
    if (response.ok) {
        return response.json();
    }
    throw new Error(response.statusText);
})
.then(data => console.log(data))
.catch(error => console.error(error));
```

*   **PHP**:
    

Copy

```
<?php
$ch = curl_init();

curl_setopt($ch, CURLOPT_URL, "{{base-url}}/wallet");
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_HTTPHEADER, [
    'X-Access-Token: {{access-token}}',
    'X-Refresh-Token: {{refresh-token}}'
]);

$response = curl_exec($ch);
$httpCode = curl_getinfo($ch, CURLINFO_HTTP_CODE);

if ($httpCode == 200) {
    echo $response;
} else {
    echo curl_error($ch);
}

curl_close($ch);
?>
```

*   **C#**:
    

Copy

```
using System;
using System.Net.Http;
using System.Threading.Tasks;

class Program
{
    static async Task Main(string[] args)
    {
        using (var client = new HttpClient())
        {
            client.DefaultRequestHeaders.Add("X-Access-Token", "{{access-token}}");
            client.DefaultRequestHeaders.Add("X-Refresh-Token", "{{refresh-token}}");

            var response = await client.GetAsync("{{base-url}}/wallet");
            if (response.IsSuccessStatusCode)
            {
                var content = await response.Content.ReadAsStringAsync();
                Console.WriteLine(content);
            }
            else
            {
                Console.WriteLine(response.ReasonPhrase);
            }
        }
    }
}
```

#### 

[](#get-customer-wallet)

Get Customer Wallet

*   **cURL**:
    

Copy

```
curl --request GET \
  --url '{{base-url}}/wallet/customer?customerId=5de468b7-de5f-414e-b948-1f2f336c3c5e' \
  --header 'X-Access-Token: {{access-token}}' \
  --header 'X-Refresh-Token: {{refresh-token}}'
```

*   **Python**:
    

Copy

```
import requests

headers = {
    'X-Access-Token': '{{access-token}}',
    'X-Refresh-Token': '{{refresh-token}}'
}

response = requests.get('{{base-url}}/wallet/customer?customerId=5de468b7-de5f-414e-b948-1f2f336c3c5e', headers=headers)
if response.status_code == 200:
    print(response.json())
else:
    print(response.reason)
```

*   **Java**:
    

Copy

```
import java.net.HttpURLConnection;
import java.net.URL;
import java.io.BufferedReader;
import java.io.InputStreamReader;

public class Main {
    public static void main(String[] args) throws Exception {
        URL url = new URL("{{base-url}}/wallet/customer?customerId=5de468b7-de5f-414e-b948-1f2f336c3c5e");
        HttpURLConnection conn = (HttpURLConnection) url.openConnection();
        conn.setRequestMethod("GET");
        conn.setRequestProperty("X-Access-Token", "{{access-token}}");
        conn.setRequestProperty("X-Refresh-Token", "{{refresh-token}}");

        int responseCode = conn.getResponseCode();
        if (responseCode == 200) {
            BufferedReader in = new BufferedReader(new InputStreamReader(conn.getInputStream()));
            String inputLine;
            StringBuilder response = new StringBuilder();
            while ((inputLine = in.readLine()) != null) {
                response.append(inputLine);
            }
            in.close();
            System.out.println(response.toString());
        } else {
            System.out.println(conn.getResponseMessage());
        }
    }
}
```

*   **JavaScript**:
    

Copy

```
const headers = {
    'X-Access-Token': '{{access-token}}',
    'X-Refresh-Token': '{{refresh-token}}'
};

fetch('{{base-url}}/wallet/customer?customerId=5de468b7-de5f-414e-b948-1f2f336c3c5e', {
    method: 'GET',
    headers: headers
})
.then(response => {
    if (response.ok) {
        return response.json();
    }
    throw new Error(response.statusText);
})
.then(data => console.log(data))
.catch(error => console.error(error));
```

*   **PHP**:
    

Copy

```
<?php
$ch = curl_init();

curl_setopt($ch, CURLOPT_URL, "{{base-url}}/wallet/customer?customerId=5de468b7-de5f-414e-b948-1f2f336c3c5e");
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_HTTPHEADER, [
    'X-Access-Token: {{access-token}}',
    'X-Refresh-Token: {{refresh-token}}'
]);

$response = curl_exec($ch);
$httpCode = curl_getinfo($ch, CURLINFO_HTTP_CODE);

if ($httpCode == 200) {
    echo $response;
} else {
    echo curl_error($ch);
}

curl_close($ch);
?>
```

*   **C#**:
    

Copy

```
using System;
using System.Net.Http;
using System.Threading.Tasks;

class Program
{
    static async Task Main(string[] args)
    {
        using (var client = new HttpClient())
        {
            client.DefaultRequestHeaders.Add("X-Access-Token", "{{access-token}}");
            client.DefaultRequestHeaders.Add("X-Refresh-Token", "{{refresh-token}}");

            var response = await client.GetAsync("{{base-url}}/wallet/customer?customerId=5de468b7-de5f-414e-b948-1f2f336c3c5e");
            if (response.IsSuccessStatusCode)
            {
                var content = await response.Content.ReadAsStringAsync();
                Console.WriteLine(content);
            }
            else
            {
                Console.WriteLine(response.ReasonPhrase);
            }
        }
    }
}
```

#### 

[](#credit-wallet)

Credit Wallet

*   **cURL**:
    

Copy

```
curl --request POST \
  --url '{{base-url}}/wallet/credit' \
  --header 'Content-Type: application/json' \
  --header 'X-Access-Token: {{access-token}}' \
  --header 'X-Refresh-Token: {{refresh-token}}' \
  --data '{
    "amount": 200,
    "reference": "14kg34dqe3rkyd23wo",
    "customerId": "d818688f-50ca-4b9c-9693-ca7c6c3988ad",
    "metadata": {
        "some-data": "sample data",
        "more-data": "any value here"
    }
}'
```

*   **Python**:
    

Copy

```
import requests

headers = {
    'X-Access-Token': '{{access-token}}',
    'X-Refresh-Token': '{{refresh-token}}',
    'Content-Type': 'application/json'
}

data = {
    "amount": 200,
    "reference": "14kg34dqe3rkyd23wo",
    "customerId": "d818688f-50ca-4b9c-9693-ca7c6c3988ad",
    "metadata": {
        "some-data": "sample data",
        "more-data": "any value here"
    }
}

response = requests.post('{{base-url}}/wallet/credit', headers=headers, json=data)
if response.status_code == 200:
    print(response.json())
else:
    print(response.reason)
```

*   **Java**:
    

Copy

```
import java.net.HttpURLConnection;
import java.net.URL;
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.io.OutputStream;

public class Main {
    public static void main(String[] args) throws Exception {
        URL url = new URL("{{base-url}}/wallet/credit");
        HttpURLConnection conn = (HttpURLConnection) url.openConnection();
        conn.setRequestMethod("POST");
        conn.setRequestProperty("X-Access-Token", "{{access-token}}");
        conn.setRequestProperty("X-Refresh-Token", "{{refresh-token}}");
        conn.setRequestProperty("Content-Type", "application/json");
        conn.setDoOutput(true);

        String jsonInputString = "{\"amount\": 200, \"reference\": \"14kg34dqe3rkyd23wo\", \"customerId\": \"d818688f-50ca-4b9c-9693-ca7c6c3988ad\", \"metadata\": {\"some-data\": \"sample data\", \"more-data\": \"any value here\"}}";
        try (OutputStream os = conn.getOutputStream()) {
            byte[] input = jsonInputString.getBytes("utf-8");
            os.write(input, 0, input.length);
        }

        int responseCode = conn.getResponseCode();
        if (responseCode == 200) {
            BufferedReader in = new BufferedReader(new InputStreamReader(conn.getInputStream()));
            String inputLine;
            StringBuilder response = new StringBuilder();
            while ((inputLine = in.readLine()) != null) {
                response.append(inputLine);
            }
            in.close();
            System.out.println(response.toString());
        } else {
            System.out.println(conn.getResponseMessage());
        }
    }
}
```

*   **JavaScript**:
    

Copy

```
const headers = {
    'X-Access-Token': '{{access-token}}',
    'X-Refresh-Token': '{{refresh-token}}',
    'Content-Type': 'application/json'
};

fetch('{{base-url}}/wallet/credit', {
    method: 'POST',
    headers: headers,
    body: JSON.stringify({
        amount: 200,
        reference: "14kg34dqe3rkyd23wo",
        customerId: "d818688f-50ca-4b9c-9693-ca7c6c3988ad",
        metadata: {
            "some-data": "sample data",
            "more-data": "any value here"
        }
    })
})
.then(response => {
    if (response.ok) {
        return response.json();
    }
    throw new Error(response.statusText);
})
.then(data => console.log(data))
.catch(error => console.error(error));
```

*   **PHP**:
    

Copy

```
<?php
$ch = curl_init();

curl_setopt($ch, CURLOPT_URL, "{{base-url}}/wallet/credit");
curl_setopt($ch, CURLOPT_POST, true);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_HTTPHEADER, [
    'X-Access-Token: {{access-token}}',
    'X-Refresh-Token: {{refresh-token}}',
    'Content-Type: application/json'
]);
curl_setopt($ch, CURLOPT_POSTFIELDS, '{"amount": 200, "reference": "14kg34dqe3rkyd23wo", "customerId": "d818688f-50ca-4b9c-9693-ca7c6c3988ad", "metadata": {"some-data": "sample data", "more-data": "any value here"}}');

$response = curl_exec($ch);
$httpCode = curl_getinfo($ch, CURLINFO_HTTP_CODE);

if ($httpCode == 200) {
    echo $response;
} else {
    echo curl_error($ch);
}

curl_close($ch);
?>
```

*   **C#**:
    

Copy

```
using System;
using System.Net.Http;
using System.Text;
using System.Threading.Tasks;

class Program
{
    static async Task Main(string[] args)
    {
        using (var client = new HttpClient())
        {
            client.DefaultRequestHeaders.Add("X-Access-Token", "{{access-token}}");
            client.DefaultRequestHeaders.Add("X-Refresh-Token", "{{refresh-token}}");

            var content = new StringContent(
                "{\"amount\": 200, \"reference\": \"14kg34dqe3rkyd23wo\", \"customerId\": \"d818688f-50ca-4b9c-9693-ca7c6c3988ad\", \"metadata\": {\"some-data\": \"sample data\", \"more-data\": \"any value here\"}}",
                Encoding.UTF8,
                "application/json"
            );

            var response = await client.PostAsync("{{base-url}}/wallet/credit", content);
            if (response.IsSuccessStatusCode)
            {
                var responseContent = await response.Content.ReadAsStringAsync();
                Console.WriteLine(responseContent);
            }
            else
            {
                Console.WriteLine(response.ReasonPhrase);
            }
        }
    }
}
```

#### 

[](#debit-wallet)

Debit Wallet

*   **cURL**:
    

Copy

```
curl --request POST \
  --url '{{base-url}}/wallet/debit' \
  --header 'Content-Type: application/json' \
  --header 'X-Access-Token: {{access-token}}' \
  --header 'X-Refresh-Token: {{refresh-token}}' \
  --data '{
    "amount": 200,
    "reference": "34k3e4f4ek4t4",
    "customerId": "aa4e9eea-d7a5-4ac2-a211-dc6d59b0c050",
    "metadata": {
        "some-data": "sample data",
        "more-data": "any value here"
    }
}'
```

*   **Python**:
    

Copy

```
import requests

headers = {
    'X-Access-Token': '{{access-token}}',
    'X-Refresh-Token': '{{refresh-token}}',
    'Content-Type': 'application/json'
}

data = {
    "amount": 200,
    "reference": "34k3e4f4ek4t4",
    "customerId": "aa4e9eea-d7a5-4ac2-a211-dc6d59b0c050",
    "metadata": {
        "some-data": "sample data",
        "more-data": "any value here"
    }
}

response = requests.post('{{base-url}}/wallet/debit', headers=headers, json=data)
if response.status_code == 200:
    print(response.json())
else:
    print(response.reason)
```

*   **Java**:
    

Copy

```
import java.net.HttpURLConnection;
import java.net.URL;
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.io.OutputStream;

public class Main {
    public static void main(String[] args) throws Exception {
        URL url = new URL("{{base-url}}/wallet/debit");
        HttpURLConnection conn = (HttpURLConnection) url.openConnection();
        conn.setRequestMethod("POST");
        conn.setRequestProperty("X-Access-Token", "{{access-token}}");
        conn.setRequestProperty("X-Refresh-Token", "{{refresh-token}}");
        conn.setRequestProperty("Content-Type", "application/json");
        conn.setDoOutput(true);

        String jsonInputString = "{\"amount\": 200, \"reference\": \"34k3e4f4ek4t4\", \"customerId\": \"aa4e9eea-d7a5-4ac2-a211-dc6d59b0c050\", \"metadata\": {\"some-data\": \"sample data\", \"more-data\": \"any value here\"}}";
        try (OutputStream os = conn.getOutputStream()) {
            byte[] input = jsonInputString.getBytes("utf-8");
            os.write(input, 0, input.length);
        }

        int responseCode = conn.getResponseCode();
        if (responseCode == 200) {
            BufferedReader in = new BufferedReader(new InputStreamReader(conn.getInputStream()));
            String inputLine;
            StringBuilder response = new StringBuilder();
            while ((inputLine = in.readLine()) != null) {
                response.append(inputLine);
            }
            in.close();
            System.out.println(response.toString());
        } else {
            System.out.println(conn.getResponseMessage());
        }
    }
}
```

*   **JavaScript**:
    

Copy

```
const headers = {
    'X-Access-Token': '{{access-token}}',
    'X-Refresh-Token': '{{refresh-token}}',
    'Content-Type': 'application/json'
};

fetch('{{base-url}}/wallet/debit', {
    method: 'POST',
    headers: headers,
    body: JSON.stringify({
        amount: 200,
        reference: "34k3e4f4ek4t4",
        customerId: "aa4e9eea-d7a5-4ac2-a211-dc6d59b0c050",
        metadata: {
            "some-data": "sample data",
            "more-data": "any value here"
        }
    })
})
.then(response => {
    if (response.ok) {
        return response.json();
    }
    throw new Error(response.statusText);
})
.then(data => console.log(data))
.catch(error => console.error(error));
```

*   **PHP**:
    

Copy

```
<?php
$ch = curl_init();

curl_setopt($ch, CURLOPT_URL, "{{base-url}}/wallet/debit");
curl_setopt($ch, CURLOPT_POST, true);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_HTTPHEADER, [
    'X-Access-Token: {{access-token}}',
    'X-Refresh-Token: {{refresh-token}}',
    'Content-Type: application/json'
]);
curl_setopt($ch, CURLOPT_POSTFIELDS, '{"amount": 200, "reference": "34k3e4f4ek4t4", "customerId": "aa4e9eea-d7a5-4ac2-a211-dc6d59b0c050", "metadata": {"some-data": "sample data", "more-data": "any value here"}}');

$response = curl_exec($ch);
$httpCode = curl_getinfo($ch, CURLINFO_HTTP_CODE);

if ($httpCode == 200) {
    echo $response;
} else {
    echo curl_error($ch);
}

curl_close($ch);
?>
```

*   **C#**:
    

Copy

```
using System;
using System.Net.Http;
using System.Text;
using System.Threading.Tasks;

class Program
{
    static async Task Main(string[] args)
    {
        using (var client = new HttpClient())
        {
            client.DefaultRequestHeaders.Add("X-Access-Token", "{{access-token}}");
            client.DefaultRequestHeaders.Add("X-Refresh-Token", "{{refresh-token}}");

            var content = new StringContent(
                "{\"amount\": 200, \"reference\": \"34k3e4f4ek4t4\", \"customerId\": \"aa4e9eea-d7a5-4ac2-a211-dc6d59b0c050\", \"metadata\": {\"some-data\": \"sample data\", \"more-data\": \"any value here\"}}",
                Encoding.UTF8,
                "application/json"
            );

            var response = await client.PostAsync("{{base-url}}/wallet/debit", content);
            if (response.IsSuccessStatusCode)
            {
                var responseContent = await response.Content.ReadAsStringAsync();
                Console.WriteLine(responseContent);
            }
            else
            {
                Console.WriteLine(response.ReasonPhrase);
            }
        }
    }
}
```

#### 

[](#freeze-customer-wallet)

Freeze Customer Wallet

*   **cURL**:
    

Copy

```
curl --request POST \
  --url '{{base-url}}/wallet/close' \
  --header 'Content-Type: application/json' \
  --header 'X-Access-Token: {{access-token}}' \
  --header 'X-Refresh-Token: {{refresh-token}}' \
  --data '{
    "customerId": "49d4ea6d-d3dc-490c-800d-7c50b89cf8ff"
}'
```

*   **Python**:
    

Copy

```
import requests

headers = {
    'X-Access-Token': '{{access-token}}',
    'X-Refresh-Token': '{{refresh-token}}',
    'Content-Type': 'application/json'
}

data = {
    "customerId": "49d4ea6d-d3dc-490c-800d-7c50b89cf8ff"
}

response = requests.post('{{base-url}}/wallet/close', headers=headers, json=data)
if response.status_code == 200:
    print(response.json())
else:
    print(response.reason)
```

*   **Java**:
    

Copy

```
import java.net.HttpURLConnection;
import java.net.URL;
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.io.OutputStream;

public class Main {
    public static void main(String[] args) throws Exception {
        URL url = new URL("{{base-url}}/wallet/close");
        HttpURLConnection conn = (HttpURLConnection) url.openConnection();
        conn.setRequestMethod("POST");
        conn.setRequestProperty("X-Access-Token", "{{access-token}}");
        conn.setRequestProperty("X-Refresh-Token", "{{refresh-token}}");
        conn.setRequestProperty("Content-Type", "application/json");
        conn.setDoOutput(true);

        String jsonInputString = "{\"customerId\": \"49d4ea6d-d3dc-490c-800d-7c50b89cf8ff\"}";
        try (OutputStream os = conn.getOutputStream()) {
            byte[] input = jsonInputString.getBytes("utf-8");
            os.write(input, 0, input.length);
        }

        int responseCode = conn.getResponseCode();
        if (responseCode == 200) {
            BufferedReader in = new BufferedReader(new InputStreamReader(conn.getInputStream()));
            String inputLine;
            StringBuilder response = new StringBuilder();
            while ((inputLine = in.readLine()) != null) {
                response.append(inputLine);
            }
            in.close();
            System.out.println(response.toString());
        } else {
            System.out.println(conn.getResponseMessage());
        }
    }
}
```

*   **JavaScript**:
    

Copy

```
const headers = {
    'X-Access-Token': '{{access-token}}',
    'X-Refresh-Token': '{{refresh-token}}',
    'Content-Type': 'application/json'
};

fetch('{{base-url}}/wallet/close', {
    method: 'POST',
    headers: headers,
    body: JSON.stringify({
        customerId: "49d4ea6d-d3dc-490c-800d-7c50b89cf8ff"
    })
})
.then(response => {
    if (response.ok) {
        return response.json();
    }
    throw new Error(response.statusText);
})
.then(data => console.log(data))
.catch(error => console.error(error));
```

*   **PHP**:
    

Copy

```
<?php
$ch = curl_init();

curl_setopt($ch, CURLOPT_URL, "{{base-url}}/wallet/close");
curl_setopt($ch, CURLOPT_POST, true);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_HTTPHEADER, [
    'X-Access-Token: {{access-token}}',
    'X-Refresh-Token: {{refresh-token}}',
    'Content-Type: application/json'
]);
curl_setopt($ch, CURLOPT_POSTFIELDS, '{"customerId": "49d4ea6d-d3dc-490c-800d-7c50b89cf8ff"}');

$response = curl_exec($ch);
$httpCode = curl_getinfo($ch, CURLINFO_HTTP_CODE);

if ($httpCode == 200) {
    echo $response;
} else {
    echo curl_error($ch);
}

curl_close($ch);
?>
```

*   **C#**:
    

Copy

```
using System;
using System.Net.Http;
using System.Text;
using System.Threading.Tasks;

class Program
{
    static async Task Main(string[] args)
    {
        using (var client = new HttpClient())
        {
            client.DefaultRequestHeaders.Add("X-Access-Token", "{{access-token}}");
            client.DefaultRequestHeaders.Add("X-Refresh-Token", "{{refresh-token}}");

            var content = new StringContent(
                "{\"customerId\": \"49d4ea6d-d3dc-490c-800d-7c50b89cf8ff\"}",
                Encoding.UTF8,
                "application/json"
            );

            var response = await client.PostAsync("{{base-url}}/wallet/close", content);
            if (response.IsSuccessStatusCode)
            {
                var responseContent = await response.Content.ReadAsStringAsync();
                Console.WriteLine(responseContent);
            }
            else
            {
                Console.WriteLine(response.ReasonPhrase);
            }
        }
    }
}
```

#### 

[](#unfreeze-customer-wallet)

Unfreeze Customer Wallet

*   **cURL**:
    

Copy

```
curl --request POST \
  --url '{{base-url}}/wallet/enable' \
  --header 'Content-Type: application/json' \
  --header 'X-Access-Token: {{access-token}}' \
  --header 'X-Refresh-Token: {{refresh-token}}' \
  --data '{
    "customerId": "49d4ea6d-d3dc-490c-800d-7c50b89cf8ff"
}'
```

*   **Python**:
    

Copy

```
import requests

headers = {
    'X-Access-Token': '{{access-token}}',
    'X-Refresh-Token': '{{refresh-token}}',
    'Content-Type': 'application/json'
}

data = {
    "customerId": "49d4ea6d-d3dc-490c-800d-7c50b89cf8ff"
}

response = requests.post('{{base-url}}/wallet/enable', headers=headers, json=data)
if response.status_code == 200:
    print(response.json())
else:
    print(response.reason)
```

*   **Java**:
    

Copy

```
import java.net.HttpURLConnection;
import java.net.URL;
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.io.OutputStream;

public class Main {
    public static void main(String[] args) throws Exception {
        URL url = new URL("{{base-url}}/wallet/enable");
        HttpURLConnection conn = (HttpURLConnection) url.openConnection();
        conn.setRequestMethod("POST");
        conn.setRequestProperty("X-Access-Token", "{{access-token}}");
        conn.setRequestProperty("X-Refresh-Token", "{{refresh-token}}");
        conn.setRequestProperty("Content-Type", "application/json");
        conn.setDoOutput(true);

        String jsonInputString = "{\"customerId\": \"49d4ea6d-d3dc-490c-800d-7c50b89cf8ff\"}";
        try (OutputStream os = conn.getOutputStream()) {
            byte[] input = jsonInputString.getBytes("utf-8");
            os.write(input, 0, input.length);
        }

        int responseCode = conn.getResponseCode();
        if (responseCode == 200) {
            BufferedReader in = new BufferedReader(new InputStreamReader(conn.getInputStream()));
            String inputLine;
            StringBuilder response = new StringBuilder();
            while ((inputLine = in.readLine()) != null) {
                response.append(inputLine);
            }
            in.close();
            System.out.println(response.toString());
        } else {
            System.out.println(conn.getResponseMessage());
        }
    }
}
```

*   **JavaScript**:
    

Copy

```
const headers = {
    'X-Access-Token': '{{access-token}}',
    'X-Refresh-Token': '{{refresh-token}}',
    'Content-Type': 'application/json'
};

fetch('{{base-url}}/wallet/enable', {
    method: 'POST',
    headers: headers,
    body: JSON.stringify({
        customerId: "49d4ea6d-d3dc-490c-800d-7c50b89cf8ff"
    })
})
.then(response => {
    if (response.ok) {
        return response.json();
    }
    throw new Error(response.statusText);
})
.then(data => console.log(data))
.catch(error => console.error(error));
```

*   **PHP**:
    

Copy

```
<?php
$ch = curl_init();

curl_setopt($ch, CURLOPT_URL, "{{base-url}}/wallet/enable");
curl_setopt($ch, CURLOPT_POST, true);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_HTTPHEADER, [
    'X-Access-Token: {{access-token}}',
    'X-Refresh-Token: {{refresh-token}}',
    'Content-Type: application/json'
]);
curl_setopt($ch, CURLOPT_POSTFIELDS, '{"customerId": "49d4ea6d-d3dc-490c-800d-7c50b89cf8ff"}');

$response = curl_exec($ch);
$httpCode = curl_getinfo($ch, CURLINFO_HTTP_CODE);

if ($httpCode == 200) {
    echo $response;
} else {
    echo curl_error($ch);
}

curl_close($ch);
?>
```

*   **C#**:
    

Copy

```
using System;
using System.Net.Http;
using System.Text;
using System.Threading.Tasks;

class Program
{
    static async Task Main(string[] args)
    {
        using (var client = new HttpClient())
        {
            client.DefaultRequestHeaders.Add("X-Access-Token", "{{access-token}}");
            client.DefaultRequestHeaders.Add("X-Refresh-Token", "{{refresh-token}}");

            var content = new StringContent(
                "{\"customerId\": \"49d4ea6d-d3dc-490c-800d-7c50b89cf8ff\"}",
                Encoding.UTF8,
                "application/json"
            );

            var response = await client.PostAsync("{{base-url}}/wallet/enable", content);
            if (response.IsSuccessStatusCode)
            {
                var responseContent = await response.Content.ReadAsStringAsync();
                Console.WriteLine(responseContent);
            }
            else
            {
                Console.WriteLine(response.ReasonPhrase);
            }
        }
    }
}
```

#### 

[](#batch-credit-customer-wallets)

Batch Credit Customer Wallets

*   **cURL**:
    

Copy

```
curl --request POST \
  --url '{{base-url}}/wallet/batch-credit-customer-wallet' \
  --header 'Content-Type: application/json' \
  --header 'X-Access-Token: {{access-token}}' \
  --header 'X-Refresh-Token: {{refresh-token}}' \
  --data '{
    "batchReference": "afsdfeadsfasrgasdfasd6",
    "transactions": [
        {
            "amount": 200,
            "reference": "afsdfeadsfasrgasdfas4d",
            "customerId": "1149d065-c5c9-4382-aec6-323090f31d9d"
        },
        {
            "amount": 4000,
            "reference": "afsdfeadsfasrgasd5fase",
            "customerId": "c938a018-8987-4411-97c5-e456868741e8"
        }
    ]
}'
```

*   **Python**:
    

Copy

```
import requests

headers = {
    'X-Access-Token': '{{access-token}}',
    'X-Refresh-Token': '{{refresh-token}}',
    'Content-Type': 'application/json'
}

data = {
    "batchReference": "afsdfeadsfasrgasdfasd6",
    "transactions": [
        {
            "amount": 200,
            "reference": "afsdfeadsfasrgasdfas4d",
            "customerId": "1149d065-c5c9-4382-aec6-323090f31d9d"
        },
        {
            "amount": 4000,
            "reference": "afsdfeadsfasrgasd5fase",
            "customerId": "c938a018-8987-4411-97c5-e456868741e8"
        }
    ]
}

response = requests.post('{{base-url}}/wallet/batch-credit-customer-wallet', headers=headers, json=data)
if response.status_code == 200:
    print(response.json())
else:
    print(response.reason)
```

*   **Java**:
    

Copy

```
import java.net.HttpURLConnection;
import java.net.URL;
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.io.OutputStream;

public class Main {
    public static void main(String[] args) throws Exception {
        URL url = new URL("{{base-url}}/wallet/batch-credit-customer-wallet");
        HttpURLConnection conn = (HttpURLConnection) url.openConnection();
        conn.setRequestMethod("POST");
        conn.setRequestProperty("X-Access-Token", "{{access-token}}");
        conn.setRequestProperty("X-Refresh-Token", "{{refresh-token}}");
        conn.setRequestProperty("Content-Type", "application/json");
        conn.setDoOutput(true);

        String jsonInputString = "{\"batchReference\": \"afsdfeadsfasrgasdfasd6\", \"transactions\": [{\"amount\": 200, \"reference\": \"afsdfeadsfasrgasdfas4d\", \"customerId\": \"1149d065-c5c9-4382-aec6-323090f31d9d\"}, {\"amount\": 4000, \"reference\": \"afsdfeadsfasrgasd5fase\", \"customerId\": \"c938a018-8987-4411-97c5-e456868741e8\"}]}";
        try (OutputStream os = conn.getOutputStream()) {
            byte[] input = jsonInputString.getBytes("utf-8");
            os.write(input, 0, input.length);
        }

        int responseCode = conn.getResponseCode();
        if (responseCode == 200) {
            BufferedReader in = new BufferedReader(new InputStreamReader(conn.getInputStream()));
            String inputLine;
            StringBuilder response = new StringBuilder();
            while ((inputLine = in.readLine()) != null) {
                response.append(inputLine);
            }
            in.close();
            System.out.println(response.toString());
        } else {
            System.out.println(conn.getResponseMessage());
        }
    }
}
```

*   **JavaScript**:
    

Copy

```
const headers = {
    'X-Access-Token': '{{access-token}}',
    'X-Refresh-Token': '{{refresh-token}}',
    'Content-Type': 'application/json'
};

fetch('{{base-url}}/wallet/batch-credit-customer-wallet', {
    method: 'POST',
    headers: headers,
    body: JSON.stringify({
        batchReference: "afsdfeadsfasrgasdfasd6",
        transactions: [
            {
                amount: 200,
                reference: "afsdfeadsfasrgasdfas4d",
                customerId: "1149d065-c5c9-4382-aec6-323090f31d9d"
            },
            {
                amount: 4000,
                reference: "afsdfeadsfasrgasd5fase",
                customerId: "c938a018-8987-4411-97c5-e456868741e8"
            }
        ]
    })
})
.then(response => {
    if (response.ok) {
        return response.json();
    }
    throw new Error(response.statusText);
})
.then(data => console.log(data))
.catch(error => console.error(error));
```

*   **PHP**:
    

Copy

```
<?php
$ch = curl_init();

curl_setopt($ch, CURLOPT_URL, "{{base-url}}/wallet/batch-credit-customer-wallet");
curl_setopt($ch, CURLOPT_POST, true);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_HTTPHEADER, [
    'X-Access-Token: {{access-token}}',
    'X-Refresh-Token: {{refresh-token}}',
    'Content-Type: application/json'
]);
curl_setopt($ch, CURLOPT_POSTFIELDS, '{"batchReference": "afsdfeadsfasrgasdfasd6", "transactions": [{"amount": 200, "reference": "afsdfeadsfasrgasdfas4d", "customerId": "1149d065-c5c9-4382-aec6-323090f31d9d"}, {"amount": 4000, "reference": "afsdfeadsfasrgasd5fase", "customerId": "c938a018-8987-4411-97c5-e456868741e8"}]}');

$response = curl_exec($ch);
$httpCode = curl_getinfo($ch, CURLINFO_HTTP_CODE);

if ($httpCode == 200) {
    echo $response;
} else {
    echo curl_error($ch);
}

curl_close($ch);
?>
```

*   **C#**:
    

Copy

```
using System;
using System.Net.Http;
using System.Text;
using System.Threading.Tasks;

class Program
{
    static async Task Main(string[] args)
    {
        using (var client = new HttpClient())
        {
            client.DefaultRequestHeaders.Add("X-Access-Token", "{{access-token}}");
            client.DefaultRequestHeaders.Add("X-Refresh-Token", "{{refresh-token}}");

            var content = new StringContent(
                "{\"batchReference\": \"afsdfeadsfasrgasdfasd6\", \"transactions\": [{\"amount\": 200, \"reference\": \"afsdfeadsfasrgasdfas4d\", \"customerId\": \"1149d065-c5c9-4382-aec6-323090f31d9d\"}, {\"amount\": 4000, \"reference\": \"afsdfeadsfasrgasd5fase\", \"customerId\": \"c938a018-8987-4411-97c5-e456868741e8\"}]}",
                Encoding.UTF8,
                "application/json"
            );

            var response = await client.PostAsync("{{base-url}}/wallet/batch-credit-customer-wallet", content);
            if (response.IsSuccessStatusCode)
            {
                var responseContent = await response.Content.ReadAsStringAsync();
                Console.WriteLine(responseContent);
            }
            else
            {
                Console.WriteLine(response.ReasonPhrase);
            }
        }
    }
}
```

#### 

[](#batch-debit-customer-wallets)

Batch Debit Customer Wallets

*   **cURL**:
    

Copy

```
curl --request POST \
  --url '{{base-url}}/wallet/batch-debit-customer-wallet' \
  --header 'Content-Type: application/json' \
  --header 'X-Access-Token: {{access-token}}' \
  --header 'X-Refresh-Token: {{refresh-token}}' \
  --data '{
    "batchReference": "88adsf8hssa43sefas8df8ahhjefasdff14",
    "transactions": [
        {
            "amount": 250,
            "reference": "dkfajdfsdjjjssd23sfjasdfasdkfjds12",
            "customerId": "a2c40f33-489c-480f-9d24-e2742502b85f"
        },
        {
            "amount": 30000,
            "reference": "dkfajdfsdjjjdsfjasd45fssasdkfjds20",
            "customerId": "cdf29144-10f7-4805-8389-3928050904f7"
        }
    ]
}'
```

*   **Python**:
    

Copy

```
import requests

headers = {
    'X-Access-Token': '{{access-token}}',
    'X-Refresh-Token': '{{refresh-token}}',
    'Content-Type': 'application/json'
}

data = {
    "batchReference": "88adsf8hssa43sefas8df8ahhjefasdff14",
    "transactions": [
        {
            "amount": 250,
            "reference": "dkfajdfsdjjjssd23sfjasdfasdkfjds12",
            "customerId": "a2c40f33-489c-480f-9d24-e2742502b85f"
        },
        {
            "amount": 30000,
            "reference": "dkfajdfsdjjjdsfjasd45fssasdkfjds20",
            "customerId": "cdf29144-10f7-4805-8389-3928050904f7"
        }
    ]
}

response = requests.post('{{base-url}}/wallet/batch-debit-customer-wallet', headers=headers, json=data)
if response.status_code == 200:
    print(response.json())
else:
    print(response.reason)
```

*   **Java**:
    

Copy

```
import java.net.HttpURLConnection;
import java.net.URL;
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.io.OutputStream;

public class Main {
    public static void main(String[] args) throws Exception {
        URL url = new URL("{{base-url}}/wallet/batch-debit-customer-wallet");
        HttpURLConnection conn = (HttpURLConnection) url.openConnection();
        conn.setRequestMethod("POST");
        conn.setRequestProperty("X-Access-Token", "{{access-token}}");
        conn.setRequestProperty("X-Refresh-Token", "{{refresh-token}}");
        conn.setRequestProperty("Content-Type", "application/json");
        conn.setDoOutput(true);

        String jsonInputString = "{\"batchReference\": \"88adsf8hssa43sefas8df8ahhjefasdff14\", \"transactions\": [{\"amount\": 250, \"reference\": \"dkfajdfsdjjjssd23sfjasdfasdkfjds12\", \"customerId\": \"a2c40f33-489c-480f-9d24-e2742502b85f\"}, {\"amount\": 30000, \"reference\": \"dkfajdfsdjjjdsfjasd45fssasdkfjds20\", \"customerId\": \"cdf29144-10f7-4805-8389-3928050904f7\"}]}";
        try (OutputStream os = conn.getOutputStream()) {
            byte[] input = jsonInputString.getBytes("utf-8");
            os.write(input, 0, input.length);
        }

        int responseCode = conn.getResponseCode();
        if (responseCode == 200) {
            BufferedReader in = new BufferedReader(new InputStreamReader(conn.getInputStream()));
            String inputLine;
            StringBuilder response = new StringBuilder();
            while ((inputLine = in.readLine()) != null) {
                response.append(inputLine);
            }
            in.close();
            System.out.println(response.toString());
        } else {
            System.out.println(conn.getResponseMessage());
        }
    }
}
```

*   **JavaScript**:
    

Copy

```
const headers = {
    'X-Access-Token': '{{access-token}}',
    'X-Refresh-Token': '{{refresh-token}}',
    'Content-Type': 'application/json'
};

fetch('{{base-url}}/wallet/batch-debit-customer-wallet', {
    method: 'POST',
    headers: headers,
    body: JSON.stringify({
        batchReference: "88adsf8hssa43sefas8df8ahhjefasdff14",
        transactions: [
            {
                amount: 250,
                reference: "dkfajdfsdjjjssd23sfjasdfasdkfjds12",
                customerId: "a2c40f33-489c-480f-9d24-e2742502b85f"
            },
            {
                amount: 30000,
                reference: "dkfajdfsdjjjdsfjasd45fssasdkfjds20",
                customerId: "cdf29144-10f7-4805-8389-3928050904f7"
            }
        ]
    })
})
.then(response => {
    if (response.ok) {
        return response.json();
    }
    throw new Error(response.statusText);
})
.then(data => console.log(data))
.catch(error => console.error(error));
```

*   **PHP**:
    

Copy

```
<?php
$ch = curl_init();

curl_setopt($ch, CURLOPT_URL, "{{base-url}}/wallet/batch-debit-customer-wallet");
curl_setopt($ch, CURLOPT_POST, true);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
curl_setopt($ch, CURLOPT_HTTPHEADER, [
    'X-Access-Token: {{access-token}}',
    'X-Refresh-Token: {{refresh-token}}',
    'Content-Type: application/json'
]);
curl_setopt($ch, CURLOPT_POSTFIELDS, '{"batchReference": "88adsf8hssa43sefas8df8ahhjefasdff14", "transactions": [{"amount": 250, "reference": "dkfajdfsdjjjssd23sfjasdfasdkfjds12", "customerId": "a2c40f33-489c-480f-9d24-e2742502b85f"}, {"amount": 30000, "reference": "dkfajdfsdjjjdsfjasd45fssasdkfjds20", "customerId": "cdf29144-10f7-4805-8389-3928050904f7"}]}');

$response = curl_exec($ch);
$httpCode = curl_getinfo($ch, CURLINFO_HTTP_CODE);

if ($httpCode == 200) {
    echo $response;
} else {
    echo curl_error($ch);
}

curl_close($ch);
?>
```

*   **C#**:
    

Copy

```
using System;
using System.Net.Http;
using System.Text;
using System.Threading.Tasks;

class Program
{
    static async Task Main(string[] args)
    {
        using (var client = new HttpClient())
        {
            client.DefaultRequestHeaders.Add("X-Access-Token", "{{access-token}}");
            client.DefaultRequestHeaders.Add("X-Refresh-Token", "{{refresh-token}}");

            var content = new StringContent(
                "{\"batchReference\": \"88adsf8hssa43sefas8df8ahhjefasdff14\", \"transactions\": [{\"amount\": 250, \"reference\": \"dkfajdfsdjjjssd23sfjasdfasdkfjds12\", \"customerId\": \"a2c40f33-489c-480f-9d24-e2742502b85f\"}, {\"amount\": 30000, \"reference\": \"dkfajdfsdjjjdsfjasd45fssasdkfjds20\", \"customerId\": \"cdf29144-10f7-4805-8389-3928050904f7\"}]}",
                Encoding.UTF8,
                "application/json"
            );

            var response = await client.PostAsync("{{base-url}}/wallet/batch-debit-customer-wallet", content);
            if (response.IsSuccessStatusCode)
            {
                var responseContent = await response.Content.ReadAsStringAsync();
                Console.WriteLine(responseContent);
            }
            else
            {
                Console.WriteLine(response.ReasonPhrase);
            }
        }
    }
}
```

#### 

[](#customer-batch-credit-customer-wallets)

Customer Batch Credit Customer Wallets

*   **cURL**:
    

Copy

```
curl --request POST \
  --url '{{base-url}}/wallet/customer-batch-credit-customer-wallet' \
  --header 'Content-Type: application/json' \
  --header 'X-Access-Token: {{access-token}}' \
  --header 'X-Refresh-Token: {{refresh-token}}' \
  --data '{
    "batchReference": "88adsf8hasefas8df8ahhjefasdff8",
    "customerId": "c938a018-8987-4411-97c5-e456868741e8",
    "recipients": [
        {
            "amount": 180,
            "reference": "dkfajdfsdjjjdsfjasdfasdkfjds9",
            "customerId": "de304d11-ca4e-491f-8851-9ca09a0084a3"
        },
        {
            "amount": 500,
            "reference": "dkfajdfsdjjjdsfjasdfasdkfjds10",
            "customerId": "f75774b0-6f99-4029-92a9-2dfe7e15d3f0"
        }
    ]
}'
```

*   **Python**:
    

Copy

```
import requests

headers = {
    'X-Access-Token': '{{access-token}}',
    'X-Refresh-Token': '{{refresh-token}}',
    'Content-Type': 'application/json'
}

data = {
    "batchReference": "88adsf8hasefas8df8ahhjefasdff8",
    "customerId": "c938a018-8987-4411-97c5-e456868741e8",
    "recipients": [
        {
            "amount": 180,
            "reference": "dkfajdfsdjjjdsfjasdfasdkfjds9",
            "customerId": "de304d11-ca4e-491f-8851-9ca09a0084a3"
        },
        {
            "amount": 500,
            "reference": "dkfajdfsdjjjdsfjasdfasdkfjds10",
            "customerId": "f75774b0-6f99-4029-92a9-2dfe7e15d3f0"
        }
    ]
}

response = requests.post('{{base-url}}/wallet/customer-batch-credit-customer-wallet', headers=headers, json=data)
if response.status_code == 200:
    print(response.json())
else:
    print(response.reason)
```

*   **Java**:
    

Copy

```
import java.net.HttpURLConnection;
import java.net.URL;
import java.io.BufferedReader;
import java.io.InputStreamReader;
import java.io.OutputStream;

public class Main {
    public static void main(String[] args) throws Exception {
        URL url = new URL("{{base-url}}/wallet/customer-batch-credit-customer-wallet");
        HttpURLConnection conn = (HttpURLConnection) url.openConnection();
        conn.setRequestMethod("POST");
        conn.setRequestProperty("X-Access-Token", "{{access-token}}");
        conn.setRequestProperty("X-Refresh-Token", "{{refresh-token}}");
        conn.setRequestProperty("Content-Type", "application/json");
        conn.setDoOutput(true);

        String jsonInputString = "{\"batchReference\": \"88adsf8hasefas8df8ahhjefasdff8\", \"customerId\": \"c938a018-8987-4411-97c5-e456868741e8\", \"recipients\": [{\"amount\": 180, \"reference\": \"dkfajdfsdjjjdsfjasdfasdkfjds9\", \"customerId\": \"de304d11-ca4e-491f-8851-9ca09a0084a3\"}, {\"amount\": 500, \"reference\": \"dkfajdfsdjjjdsfjasdfasdkfjds10\", \"customerId\": \"f75774b0-6f99-4029-92a9-2dfe7e15d3f0\"}]}";
        try (OutputStream os = conn.getOutputStream()) {
            byte[] input = jsonInputString.getBytes("utf-8");
            os.write(input, 0, input.length);
        }

        int responseCode = conn.getResponseCode();
        if (responseCode == 200) {
            BufferedReader in
```

[PreviousGet Merchant Wallet](/xpress-wallet-api/merchant/get-merchant-wallet)[NextAPI Reference](/reference/api-reference)

Last updated 26 days ago