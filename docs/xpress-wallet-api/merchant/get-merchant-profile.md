# Get Merchant Profile

Retrieve the profile of the logged-in merchant.

*   **Endpoint**: `GET {{base-url}}/merchant/profile`
    
*   **Headers**:
    
    Copy
    
    ```
    {
      "Authorization": "Bearer {{vault:authorization-secret}}",
      "X-Access-Token": "{{access-token}}",
      "X-Refresh-Token": "{{refresh-token}}"
    }
    ```
    
*   **Response**:
    
    *   **200 OK**:
        
        Copy
        
        ```
        {
          "status": true,
          "data": {
            "id": "c56d9ba0-588b-43ef-9ba5-9e70e2187180",
            "bvn": null,
            "slug": "IDS",
            "email": "[email protected]",
            "phoneNumber": "2347065948710",
            "callbackURL": "https://656c12875b57.ngrok.io/v1/webhook/test",
            "businessName": "Herlabytes",
            "businessType": "FINANCIAL-SERVICES",
            "merchantType": "PLATINUM",
            "review": "PENDING",
            "walletReservationCharge": 20,
            "bvnChargeV1": 0,
            "bvnVerificationCharge": 40,
            "walletToWalletTransfer": 20,
            "airtimeCharge": 10,
            "transferCharges": {
              "max5000": 20,
              "max50000": 35,
              "min50000": 52
            },
            "contractCode": null,
            "apiKey": null,
            "mode": "SANDBOX",
            "fundingRate": 0.85,
            "fundingRateMax": 200,
            "sandboxCallbackURL": "https://656c12875b57.ngrok.io/v1/webhook/test",
            "tier_1_daily_limit": 10000,
            "tier_2_daily_limit": 200000,
            "tier_3_daily_limit": 1000000000,
            "tier_1_min_balance": 0,
            "tier_2_min_balance": 0,
            "tier_3_min_balance": 0,
            "baseCustomerWalletCredit": 1200,
            "canLogin": true,
            "sendEmail": true,
            "autoCardFunding": false,
            "createdAt": "2021-01-27T12:25:16.761Z",
            "updatedAt": "2021-03-03T00:11:15.548Z"
          }
        }
        ```
        
    
*   **Sample Code (Dart)**:
    
    Copy
    
    ```
    var headers = {
      'X-Access-Token': '{{access-token}}',
      'X-Refresh-Token': '{{refresh-token}}'
    };
    var request = http.Request('GET', Uri.parse('{{base-url}}/merchant/profile'));
    request.headers.addAll(headers);
    http.StreamedResponse response = await request.send();
    if (response.statusCode == 200) {
      print(await response.stream.bytesToString());
    } else {
      print(response.reasonPhrase);
    }
    ```
    

[PreviousComplete Merchant KYC](/xpress-wallet-api/merchant/complete-merchant-kyc)[NextUpdate Merchant Profile](/xpress-wallet-api/merchant/update-merchant-profile)

Last updated 26 days ago