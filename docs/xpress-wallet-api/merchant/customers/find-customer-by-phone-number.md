# Find Customer by Phone Number

Retrieve customer details using their phone number.

*   **Endpoint**: `GET {{base-url}}/customer/phone?phoneNumber={phoneNumber}`
    
*   **Query Parameters**:
    
    *   `phoneNumber`: The customer's phone number (e.g., `08020245350`).
        
    
*   **Headers**:

    ```
    {
      "X-Access-Token": "{{access-token}}",
      "X-Refresh-Token": "{{refresh-token}}"
    }
    ```
    
*   **Response**:
    
    *   **200 OK**:

        ```
        {
          "status": true,
          "customer": {
            "id": "1149d065-c5c9-4382-aec6-323090f31d9d",
            "firstName": "Emma",
            "lastName": "Godwin",
            "walletId": "0bea0968-c43a-47fe-a83a-f7b514194aba"
          }
        }
        ```
        
    
*   **Sample Code (Dart)**:

    ```
    var headers = {
      'X-Access-Token': '{{access-token}}',
      'X-Refresh-Token': '{{refresh-token}}'
    };
    var request = http.Request('GET', Uri.parse('{{base-url}}/customer/phone?phoneNumber=08030223346'));
    request.headers.addAll(headers);
    http.StreamedResponse response = await request.send();
    if (response.statusCode == 200) {
      print(await response.stream.bytesToString());
    } else {
      print(response.reasonPhrase);
    }
    ```
    

[PreviousGet Customer Details](/xpress-wallet-api/merchant/customers/get-customer-details)[NextUpdate Customer Profile](/xpress-wallet-api/merchant/customers/update-customer-profile)