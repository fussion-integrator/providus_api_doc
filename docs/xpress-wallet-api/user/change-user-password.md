# Change user password

#### 

[](#put-user-password)

PUT /user/password

Changes the password of the authenticated user.

**Request Headers:**

*   X-Access-Token: Access token
    
*   X-Refresh-Token: Refresh token
    

**Request Body:**

Copy

```
{
  "password": "password"
}
```

**Example Request (Dart - http):**

Copy

```
var headers = {
  'X-Access-Token': '{{access-token}}',
  'X-Refresh-Token': '{{refresh-token}}'
};
var request = http.Request('PUT', Uri.parse('{{base-url}}/user/password'));
request.body = '''{\n    "password": "123456"\n}''';
request.headers.addAll(headers);
http.StreamedResponse response = await request.send();
if (response.statusCode == 200) {
  print(await response.stream.bytesToString());
} else {
  print(response.reasonPhrase);
}
```

**Response (200 OK):**

Copy

```
{
  "status": true,
  "message": "Password successfully changed."
}
```

### 

[](#undefined)

[PreviousGet user profile](/xpress-wallet-api/user/get-user-profile)[NextMerchant](/xpress-wallet-api/merchant)

Last updated 1 month ago