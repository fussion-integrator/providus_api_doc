# Reset password

#### 

[](#post-auth-password-reset)

POST /auth/password/reset

Resets the user password using a reset code.

**Request Body:**

```
{
  "resetCode": "3122489",
  "password": "password"
}
```

**Example Request (Dart - http):**

```
var headers = {};
var request = http.Request('POST', Uri.parse('{{base-url}}/merchant/change-merchant-password'));
request.body = '''{\n\t"resetCode":"3122489",\n\t"password":"password"\n}''';
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
  "message": "Password reset successfully"
}
```

[PreviousForget Password](/xpress-wallet-api/authentication/forget-password)[NextRefresh Token](/xpress-wallet-api/authentication/refresh-token)

Last updated 1 month ago