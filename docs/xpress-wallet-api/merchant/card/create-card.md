# Create Card

Create a new card for a customer.

*   **Endpoint**: `POST {{base-url}}/card`
    
*   **Headers**:
    
    Copy
    
    ```
    {
      "X-Access-Token": "{{access-token}}",
      "X-Refresh-Token": "{{refresh-token}}"
    }
    ```
    
*   **Body**:
    
    Copy
    
    ```
    {
      "address1": "10 Sonola Street, Osogbo",
      "address2": "20 Sonola Street, Osogbo",
      "customerId": "aa4e9eea-d7a5-4ac2-a211-dc6d59b0c050"
    }
    ```
    
*   **Response**:
    
    *   **200 OK**:
        
        Copy
        
        ```
        {
          "status": true,
          "message": "Card created successfully."
        }
        ```
        
    
*   **Sample Code (Dart)**:
    
    Copy
    
    ```
    var headers = {
      'X-Access-Token': '{{access-token}}',
      'X-Refresh-Token': '{{refresh-token}}'
    };
    var request = http.Request('POST', Uri.parse('{{base-url}}/card'));
    request.body = '''{
      "address1": "10 Sonola Street, Osogbo",
      "address2": "20 Sonola Street, Osogbo",
      "customerId": "c938a018-8987-4411-97c5-e456868741e8"
    }''';
    request.headers.addAll(headers);
    http.StreamedResponse response = await request.send();
    if (response.statusCode == 200) {
      print(await response.stream.bytesToString());
    } else {
      print(response.reasonPhrase);
    }
    ```
    

[PreviousCard Setup](/xpress-wallet-api/merchant/card/card-setup)[NextActivate Card](/xpress-wallet-api/merchant/card/activate-card)

Last updated 26 days ago