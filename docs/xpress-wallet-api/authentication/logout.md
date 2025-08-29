# Logout

#### 

[](#post-auth-logout)

POST /auth/logout

Logs out the authenticated user.

**Request:**No body required.

**Example Request (Dart - http):**

```
var request = http.Request('POST', Uri.parse('{{base-url}}/auth/logout'));
http.StreamedResponse response = await request.send();
if (response.statusCode == 200) {
  print(await response.stream.bytesToString());
} else {
  print(response.reasonPhrase);
}
```

#### 

[](#undefined)

[PreviousLogin](/xpress-wallet-api/authentication/login)[NextForget Password](/xpress-wallet-api/authentication/forget-password)