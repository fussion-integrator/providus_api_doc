# Get All Customers

Retrieve a paginated list of all customers associated with the merchant.

*   **Endpoint**: `GET {{base-url}}/customer`
    
*   **Query Parameters**:
    
    *   `page`: Page number (e.g., `1`).
        
    

**Headers**:

```
{
  "Authorization": "Bearer {{vault:authorization-secret}}",
  "X-Access-Token": "{{access-token}}",
  "X-Refresh-Token": "{{refresh-token}}"
}
```

**Response**:

**200 OK**:

```
{
  "status": true,
  "customers": [
    {
      "id": "1149d065-c5c9-4382-aec6-323090f31d9d",
      "bvn": "22192640723",
      "firstName": "Emma",
      "lastName": "Godwin",
      "BVNLastName": "OBAGUNWA",
      "BVNFirstName": "EMMANUEL",
      "email": "[email protected]",
      "nameMatch": false,
      "phoneNumber": "08030223346",
      "dateOfBirth": "1991-09-13",
      "createdAt": "2020-09-16T12:01:51.520Z",
      "updatedAt": "2020-09-16T12:01:51.520Z",
      "walletId": "0bea0968-c43a-47fe-a83a-f7b514194aba"
    },
    ...
  ],
  "metadata": {
    "page": 1,
    "totalRecords": 7,
    "totalPages": 1
  }
}
```

### 

[](#sample-implementation)

Sample Implementation

Curl

[](#tab-curl)

Dart

[](#tab-dart)

Python

[](#tab-python)

Java

[](#tab-java)

JavaScript

[](#tab-javascript)

PHP

[](#tab-php)

```
curl --request GET \
  --url '{{base-url}}/customer?page=1' \
  --header 'X-Access-Token: {{access-token}}' \
  --header 'X-Refresh-Token: {{refresh-token}}'
```

```
// Some code
```

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

#### 

[](#undefined-1)

[PreviousCustomers](/xpress-wallet-api/merchant/customers)[NextGet Customer Details](/xpress-wallet-api/merchant/customers/get-customer-details)

Last updated 26 days ago