# Get All Wallets

Retrieve a list of all customer wallets.

*   **Endpoint**: `GET {{base-url}}/wallet`
    
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
          "wallets": [
            {
              "email": "[email protected]",
              "id": "2ac94bae-90cb-4dd4-852c-93169980d00a",
              "lastName": "Customer",
              "firstName": "Demo",
              "status": "ACTIVE",
              "bankName": "Providus Bank",
              "bankCode
        ```
        
    

[PreviousCreate Customer Wallet](/xpress-wallet-api/merchant/wallet/create-customer-wallet)[NextTransactions](/xpress-wallet-api/merchant/transactions)

Last updated 26 days ago