# Card Setup

Configure card settings for a merchant.

*   **Endpoint**: `PUT {{base-url}}/card/setup`
    
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
      "appId": "test",
      "appKey": "test",
      "prepaidCardPrefix": "5061000110195",
      "loadingAccountName": "Emmanuel Adeniyi",
      "loadingAccountNumber": "1029384857",
      "loadingAccountSortcode": "001256"
    }
    ```
    
*   **Response**:
    
    *   **200 OK**:

        ```
        {
          "status": true,
          "message": "Card setup information successfully updated."
        }
        ```
        
    
*   **Sample Code (Dart)**:

    ```
    var headers = {
      'X-Access-Token': '{{access-token}}',
      'X-Refresh-Token': '{{refresh-token}}'
    };
    var request = http.Request('PUT', Uri.parse('{{base-url}}/card/setup'));
    request.body = '''{
      "appId": "test",
      "appKey": "test",
      "prepaidCardPrefix": "5061000110195",
      "loadingAccountName": "Emmanuel Adeniyi",
      "loadingAccountNumber": "1029384857",
      "loadingAccountSortcode": "001256"
    }''';
    request.headers.addAll(headers);
    http.StreamedResponse response = await request.send();
    if (response.statusCode == 200) {
      print(await response.stream.bytesToString());
    } else {
      print(response.reasonPhrase);
    }
    ```
    

[PreviousCard](/xpress-wallet-api/merchant/card)[NextCreate Card](/xpress-wallet-api/merchant/card/create-card)