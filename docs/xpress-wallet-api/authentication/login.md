# Login

#### 

[](#post-auth-login)

POST /auth/login

Logs in a merchant user and returns user and merchant details.

**Request Body:**

```
{
  "email": "bWVyY2hhbnQxQG1haWxpbmF0b3IuY29t",
  "password": "cGFzc3dvcmQ="
}
```

**Example Request (Dart - http):**

```
var request = http.Request('POST', Uri.parse('{{base-url}}/auth/login'));
request.body = '''{\n\t"email": "bWVyY2hhbnQxQG1haWxpbmF0b3IuY29t",\n\t"password": "cGFzc3dvcmQ="\n}''';

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
    "updatedAt": "2022-05-03T11:01:11.923Z"
  },
  "merchant": {
    "email": "[email protected]",
    "id": "e84a4677-3158-40ba-8967-f523c2315cf9",
    "lastName": "Obagunwa",
    "mode": "SANDBOX",
    "role": "Admin",
    "firstName": "Samson",
    "owner": false,
    "review": "PENDING",
    "callbackURL": null,
    "businessName": "Caleb",
    "businessType": "Restaurants",
    "parentMerchant": null,
    "canDebitCustomer": false,
    "sandboxCallbackURL": null,
    "createdAt": "2022-05-03T10:18:19.172Z",
    "updatedAt": "2022-05-03T10:18:19.172Z"
  }
}
```

#### 

[](#undefined)

[PreviousAuthentication](/xpress-wallet-api/authentication)[NextLogout](/xpress-wallet-api/authentication/logout)

Last updated 1 month ago