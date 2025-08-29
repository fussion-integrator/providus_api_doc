# Forget Password

#### 

[](#post-auth-password-forget)

POST /auth/password/forget

Initiates a password reset by sending a reset code to the provided email.

**Request Body:**

```
{
  "email": "[email protected]"
}
```

**Example Request (Dart - http):**

```
var headers = {
  'Authorization': '{{vault:bearer-token}}'
};
var request = http.Request('POST', Uri.parse('{{base-url}}/merchant/request-merchant-password-change'));
request.body = '''{\n\t"email":"[email protected]"\n}''';
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
  "message": "Your reset code has been sent to your email. It expires in 24 hours."
}
```

[PreviousLogout](/xpress-wallet-api/authentication/logout)[NextReset password](/xpress-wallet-api/authentication/reset-password)