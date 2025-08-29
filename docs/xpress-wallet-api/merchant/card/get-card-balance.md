# Get Card Balance

Retrieve the balance and limits of a customer's card.

*   **Endpoint**: `GET {{base-url}}/card/balance?customerId={customerId}`
    
*   **Query Parameters**:
    
    *   `customerId`: The customer's unique ID (e.g., `aa4e9eea-d7a5-4ac2-a211-dc6d59b0c050`).
        
    
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
          "data": {
            "id": "b2c1552e-f8e0-4e58-8a1a-d62ddde08133",
            "ledgerBalance": "120000",
            "availableBalance": "6723",
            "goodsLimit": "1400000",
            "goodsNrTransLimit": "5",
            "cashLimit": "0",
            "cashNrTransLimit": "0",
            "paymentLimit": "1400000",
            "paymentNrTransLimit": "5",
            "cardNotPresentLimit": "1400000",
            "depositCreditLimit": "1000000",
            "updatedAt": "2020-10-19T15:25:13.501Z",
            "createdAt": "2020-10-19T15:25:13.501Z",
            "deletedAt": null
          }
        }
        ```
        
    
*   **Sample Code (Dart)**:

    ```
    var headers = {
      'X-Access-Token': '{{access-token}}',
      'X-Refresh-Token': '{{refresh-token}}'
    };
    var request = http.Request('GET', Uri.parse('{{base-url}}/card/balance?last6=000352'));
    request.headers.addAll(headers);
    http.StreamedResponse response = await request.send();
    if (response.statusCode == 200) {
      print(await response.stream.bytesToString());
    } else {
      print(response.reasonPhrase);
    }
    ```
    

[PreviousActivate Card](/xpress-wallet-api/merchant/card/activate-card)[NextFund Card](/xpress-wallet-api/merchant/card/fund-card)