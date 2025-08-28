# Activate Card

Activate a card for a customer.

*   **Endpoint**: `POST {{base-url}}/card/activate`
    
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
      "amount": 200,
      "last6": "202010",
      "customerId": "aa4e9eea-d7a5-4ac2-a211-dc6d59b0c050"
    }
    ```
    
*   **Response**:
    
    *   **200 OK**:
        
        Copy
        
        ```
        {
          "status": true,
          "message": "Card activated successfully."
        }
        ```
        
    
*   **Sample Code (Dart)**:
    
    Copy
    
    ```
    var headers = {
      'X-Access-Token': '{{access-token}}',
      'X-Refresh-Token': '{{refresh-token}}'
    };
    var request = http.Request('POST', Uri.parse('{{base-url}}/card/activate'));
    request.body = '''{
      "last6": "000352",
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
    

[PreviousCreate Card](/xpress-wallet-api/merchant/card/create-card)[NextGet Card Balance](/xpress-wallet-api/merchant/card/get-card-balance)

Last updated 26 days ago