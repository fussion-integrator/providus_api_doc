# Get user profile

#### 

[](#get-user-profile)

GET /user/profile

Retrieves the profile details of the authenticated merchant.

**Request Headers:**

*   X-Access-Token: Access token
    
*   X-Refresh-Token: Refresh token
    

**Example Request (Dart - http):**

```
var headers = {
  'X-Access-Token': '{{access-token}}',
  'X-Refresh-Token': '{{refresh-token}}'
};
var request = http.Request('GET', Uri.parse('{{base-url}}/user/profile'));
request.headers.addAll(headers);
http.StreamedResponse response = await request.send();
if (response.statusCode == 200) {
  print(await response.stream.bytesToString());
} else {
  print(response.reasonPhrase);
}
```

**Response (200 OK):**

```
{
  "status": true,
  "data": {
    "id": "425bc461-9b6c-4036-b47a-9d96e4f21eba",
    "role": "USER",
    "email": "[email protected]",
    "lastName": "Obagunwa",
    "firstName": "Samson",
    "phoneNumber": "2348020245368",
    "MerchantId": "e84a4677-3158-40ba-8967-f523c2315cf9",
    "createdAt": "2021-08-16T22:59:27.026Z",
    "updatedAt": "2022-05-03T11:01:11.923Z",
    "Merchant": {
      "id": "e84a4677-3158-40ba-8967-f523c2315cf9",
      "email": "[email protected]",
      "review": "PENDING",
      "businessName": "Caleb",
      "canDebitCustomer": false,
      "parentMerchant": null,
      "createdAt": "2022-05-03T10:18:19.172Z",
      "mode": "SANDBOX",
      "owner": false
    }
  },
  "permissions": [
    "BROWSE_CUSTOMERS",
    "UPDATE_CUSTOMERS",
    "CREATE_CUSTOMER_WALLET",
    "WALLET_CREDIT_DEBIT",
    "MANAGE_BALANCE_SETTLEMENT",
    "BROWSE_MERCHANT_WALLET",
    "ENABLE_DISABLE_WALLET",
    "SET_TRANSACTION_PIN",
    "MANAGE_TRANSFER",
    "BROWSE_TRANSACTIONS",
    "UPDATE_MERCHANT_DETAIL",
    "BROWSE_KEYS",
    "GENERATE_KEYS",
    "MANAGE_AIRTIME",
    "MANAGE_PREPAID_CARD",
    "INVITE_TEAM_MEMBER",
    "BROWSE_ROLES",
    "MANAGE_ROLES",
    "MANAGE_TEAM_MEMBER",
    "BROWSE_TEAM_MEMBER"
  ]
}
```

[PreviousUser](/xpress-wallet-api/user)[NextChange user password](/xpress-wallet-api/user/change-user-password)