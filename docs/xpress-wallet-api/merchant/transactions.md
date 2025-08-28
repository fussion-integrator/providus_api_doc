# Transactions

#### 

[](#get-batch-transaction-details)

Get Batch Transaction Details

Retrieve details of a specific batch transaction using a reference ID.

*   **Endpoint**: `GET {{base-url}}/transaction/batch/:reference`
    
*   **Path Parameters**:
    
    *   `reference`: The unique transaction reference (e.g., `8ede8w340ddk3erowr3ef63`).
        
    
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
            "id": "1",
            "type": "DEBIT",
            "source": "Merchant",
            "reference": "8ede8w340ddk3erowr3ef63",
            "status": "SUCCESS",
            "passed": ["ref1", "ref2"],
            "failed": [],
            "createdAt": "2023-01-01T12:00:00Z",
            "updatedAt": "2023-01-01T12:00:00Z"
          }
        }
        ```
        
    
*   **Sample Code (Dart)**:

    ```
    var headers = {
      'X-Access-Token': '{{access-token}}',
      'X-Refresh-Token': '{{refresh-token}}'
    };
    var request = http.Request('GET', Uri.parse('{{base-url}}/transaction/batch/8ede8w340ddk3erowr3ef63'));
    request.headers.addAll(headers);
    http.StreamedResponse response = await request.send();
    if (response.statusCode == 200) {
      print(await response.stream.bytesToString());
    } else {
      print(response.reasonPhrase);
    }
    ```
    

[PreviousGet All Wallets](/xpress-wallet-api/merchant/wallet/get-all-wallets)[NextTransfer](/xpress-wallet-api/merchant/transfer)

Last updated 26 days ago