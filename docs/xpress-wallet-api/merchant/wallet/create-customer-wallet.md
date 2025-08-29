# Create Customer Wallet

Create a wallet for a customer.

*   **Endpoint**: `POST {{base-url}}/wallet`
    
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
      "bvn": "22181029322",
      "firstName": "First",
      "lastName": "User",
      "dateOfBirth": "1992-05-16",
      "phoneNumber": "08020245368",
      "email": "[email protected]",
      "address": "No 10, Adewale Ajasin University",
      "metadata": {
        "even-more": "Other data",
        "additional-data": "some more data"
      }
    }
    ```
    
*   **Response**:
    
    *   **200 OK**:

        ```
        {
          "status": true,
          "customer": {
            "id": "5de468b7-de5f-414e-b948-1f2f336c3c5e",
            "metadata": {
              "even-more": "Other data",
              "additional-data": "some more data"
            },
            "bvn": "22181029312",
            "currency": "NGN",
            "dateOfBirth": "1992-05-16",
            "phoneNumber": "08020245356",
            "lastName": "Adekunle",
            "firstName": "Ridwan",
            "BVNLastName": "Adekunle",
            "BVNFirstName": "Ridwan",
            "nameMatch": true,
            "email": "[email protected]",
            "mode": "SANDBOX",
            "MerchantId": "c56d9ba0-588b-43ef-9ba5-9e70e2187180",
            "tier": "TIER_2",
            "updatedAt": "2021-02-22T16:32:01.468Z",
            "createdAt": "2021-02-22T16:32:01.468Z",
            "address": null
          },
          "wallet": {
            "id": "0080bd12-0d81-4b9d-9e0b-74c670e09c53",
            "mode": "SANDBOX",
            "email": "[email protected]",
            "currency": "NGN",
            "bankName": "Providus Bank",
            "bankCode": "000023",
            "accountName": "MERCHANT(ids-ridwan adekunle)",
            "accountNumber": "9964189288",
            "accountReference": "xX1jAsqtUHnM4epteTrcDTGWL",
            "updatedAt": "2021-02-22T16:32:04.361Z",
            "createdAt": "2021-02-22T16:32:04.361Z",
            "bookedBalance": 0,
            "availableBalance": 0,
            "status": "ACTIVE",
            "updated": false,
            "walletType": "Customers",
            "walletId": "5de468b7-de5f-414e-b948-1f2f336c3c5e"
          }
        }
        ```
        
    
*   **Sample Code (Dart)**:

    ```
    var headers = {
      'X-Access-Token': '{{access-token}}',
      'X-Refresh-Token': '{{refresh-token}}'
    };
    var request = http.Request('POST', Uri.parse('{{base-url}}/wallet'));
    request.body = '''{
      "bvn": "22181029312",
      "firstName": "Ridwan",
      "lastName": "Adekunle",
      "dateOfBirth": "1992-05-16",
      "phoneNumber": "08020245356",
      "address": "No 10, Adewale Ajasin University",
      "metadata": {
        "even-more": "Other data",
        "additional-data": "some more data"
      }
    }''';
    request.headers.addAll(headers);
    http.StreamedResponse response = await request.send();
    if (response.statusCode == 200) {
      print(await response.stream.bytesToString());
    } else {
      print(response.reasonPhrase);
    }
    ```
    

[PreviousWallet](/xpress-wallet-api/merchant/wallet)[NextGet All Wallets](/xpress-wallet-api/merchant/wallet/get-all-wallets)