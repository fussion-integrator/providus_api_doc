# Fund Card

Add funds to a customer's card.

*   **Endpoint**: `POST {{base-url}}/card/fund`
    
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
      "amount": 150,
      "customerId": "9093ac1f-74e9-499b-bf5e-0bdf9c6c9a20"
    }
    ```
    
*   **Response**:
    
    *   **200 OK**:

        ```
        {
          "status": true,
          "message": "Card funded successfully."
        }
        ```
        
    
*   **Sample Code (Dart)**:

    ```
    var headers = {
      'X-Access-Token': '{{access-token}}',
      'X-Refresh-Token': '{{refresh-token}}'
    };
    var request = http.Request('POST', Uri.parse('{{base-url}}/card/fund'));
    request.body = '''{
      "amount": 100,
      "customerId": "ce43795c-f90f-40cf-b46e-1e1c49abf110"
    }''';
    request.headers.addAll(headers);
    http.StreamedResponse response = await request.send();
    if (response.statusCode == 200) {
      print(await response.stream.bytesToString());
    } else {
      print(response.reasonPhrase);
    }
    ```
    

[PreviousGet Card Balance](/xpress-wallet-api/merchant/card/get-card-balance)[NextTeam](/xpress-wallet-api/merchant/team)