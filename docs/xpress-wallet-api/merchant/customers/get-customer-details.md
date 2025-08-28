# Get Customer Details

Retrieve details of a specific customer by their ID.

*   **Endpoint**: `GET {{base-url}}/customer/:customerId`
    
*   **Path Parameters**:
    
    *   `customerId`: The unique ID of the customer (e.g., `d5e31dbd-ec51-4932-86a6-d92ee5a49957`).
        
    
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
          }
        }
        ```
        
    
*   **Sample Code (Dart)**:

    ```
    var headers = {
      'X-Access-Token': '{{access-token}}',
      'X-Refresh-Token': '{{refresh-token}}'
    };
    var request = http.Request('GET', Uri.parse('{{base-url}}/customer/1149d065-c5c9-4382-aec6-323090f31d9d'));
    request.headers.addAll(headers);
    http.StreamedResponse response = await request.send();
    if (response.statusCode == 200) {
      print(await response.stream.bytesToString());
    } else {
      print(response.reasonPhrase);
    }
    ```
    

[PreviousGet All Customers](/xpress-wallet-api/merchant/customers/get-all-customers)[NextFind Customer by Phone Number](/xpress-wallet-api/merchant/customers/find-customer-by-phone-number)

Last updated 26 days ago