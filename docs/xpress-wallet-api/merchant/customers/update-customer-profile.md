# Update Customer Profile

Update a customer's profile information.

*   **Endpoint**: `PUT {{base-url}}/customer/{customerId}`
    
*   **Path Parameters**:
    
    *   `customerId`: The unique ID of the customer (e.g., `6834b937-bdf0-430e-9600-90009cd5c92e`).
        
    
*   **Headers**:

    ```
    {
      "X-Access-Token": "{{access-token}}",
      "X-Refresh-Token": "{{refresh-token}}"
    }
    ```
    
*   **Body**:

    ```
    {
      "firstName": "Updated",
      "lastName": "James",
      "address": "No 10, Adewale street",
      "phoneNumber": "08048584833",
      "metadata": {
        "others": "anything"
      }
    }
    ```
    
*   **Response**:
    
    *   **200 OK**:

        ```
        {
          "status": true,
          "customer": {
            "firstName": "Updated",
            "lastName": "Customer",
            "email": "[email protected]",
            "phoneNumber": "08030223344",
            "dateOfBirth": "1991-09-13"
          }
        }
        ```
        
    
*   **Sample Code (Dart)**:

    ```
    var headers = {
      'X-Access-Token': '{{access-token}}',
      'X-Refresh-Token': '{{refresh-token}}'
    };
    var request = http.Request('PUT', Uri.parse('{{base-url}}/customer/49d4ea6d-d3dc-490c-800d-7c50b89cf8ff'));
    request.body = '''{
      "firstName": "Updated"
    }''';
    request.headers.addAll(headers);
    http.StreamedResponse response = await request.send();
    if (response.statusCode == 200) {
      print(await response.stream.bytesToString());
    } else {
      print(response.reasonPhrase);
    }
    ```
    

[PreviousFind Customer by Phone Number](/xpress-wallet-api/merchant/customers/find-customer-by-phone-number)[NextWallet](/xpress-wallet-api/merchant/wallet)