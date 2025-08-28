# Refresh Token

#### 

[](#post-auth-refresh-token)

POST /auth/refresh/token

Refreshes authentication tokens for the user.

**Request Headers:**

*   X-Refresh-Token: Refresh token (e.g., Cx9AH9ubWqG3JyBz8DZr-E6aTa8GKruNerzJRCDUFbyjM6ef)
    

**Example Request (Dart - http):**

```
var headers = {
  'X-Refresh-Token': 'Cx9AH9ubWqG3JyBz8DZr-E6aTa8GKruNerzJRCDUFbyjM6ef'
};
var request = http.Request('POST', Uri.parse('{{base-url}}/auth/refresh/token'));
request.body = '''''';
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
    "createdAt": "2021-08-16T22:59:27.026Z",
    "updatedAt": "2021-08-16T22:59:27.026Z"
  },
  "merchant": {
    "role": "USER",
    "email": "[email protected]",
    "id": "fb2b0eb6-edc8-48f8-bc38-5c000e52a57e",
    "lastName": "Obagunwa",
    "mode": "SANDBOX",
    "firstName": "Samson",
    "review": "ENABLED",
    "callbackURL": "https://webhook.site/7e4f1819-7780-416d-8596-3dece233d785",
    "businessName": "Neyosoft",
    "businessType": "Electrical Electronics",
    "parentMerchant": "0cee2057-645e-48aa-b2f7-712e07cd0232",
    "canDebitCustomer": true,
    "sandboxCallbackURL": "http://localhost:50004/webhook/wallet",
    "createdAt": "2021-08-16T22:59:26.765Z",
    "updatedAt": "2022-01-31T17:39:36.193Z"
  }
}
```

### 

[](#undefined)

[PreviousReset password](/xpress-wallet-api/authentication/reset-password)[NextUser](/xpress-wallet-api/user)

Last updated 1 month ago