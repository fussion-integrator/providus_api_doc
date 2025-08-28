# Switch Merchant

Switch the active merchant account.

*   **Endpoint**: `POST {{base-url}}/team/merchants/switch`
    
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
      "merchantId": "0cee2057-645e-48aa-b2f7-712e07cd0232"
    }
    ```
    
*   **Response**:
    
    *   **200 OK**:

        ```
        {
          "status": true,
          "message": "Merchant successfully switched."
        }
        ```
        
    
*   **Sample Code (Dart)**:

    ```
    var headers = {
      'X-Access-Token': '{{access-token}}',
      'X-Refresh-Token': '{{refresh-token}}'
    };
    var request = http.Request('POST', Uri.parse('{{base-url}}/team/merchants/switch'));
    request.body = '''{
      "merchantId": "151b73ed-93b8-4ed8-9288-6e290c2af38e"
    }''';
    request.headers.addAll(headers);
    http.StreamedResponse response = await request.send();
    if (response.statusCode == 200) {
      print(await response.stream.bytesToString());
    } else {
      print(response.reasonPhrase);
    }
    ```
    

[PreviousGet Merchant List](/xpress-wallet-api/merchant/team/get-merchant-list)[NextUpdate Member Information](/xpress-wallet-api/merchant/team/update-member-information)

Last updated 26 days ago