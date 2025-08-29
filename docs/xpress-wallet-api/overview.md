# Xpress Wallet API

The Xpress Wallet API allows seamless integration of wallet functionalities into your products. Build smarter and faster applications with features for authentication, user management, merchant operations, and wallet transactions. This API operates in both sandbox and production modes, with endpoints designed to handle user authentication, customer management, and merchant wallet details.

#### 

[](#how-it-works)

How It Works

*   **Authentication**: Obtain access and refresh tokens via the login endpoint.
    
*   **User Management**: Manage user profiles and passwords.
    
*   **Merchant Operations**: Handle merchant registration, profile updates, KYC, and access key generation.
    
*   **Wallet Management**: Retrieve merchant wallet details and customer information.
    

#### 

[](#objectives)

Objectives

*   Enable secure login and token management.
    
*   Provide tools for managing merchant and customer data.
    
*   Facilitate wallet-related transactions and profiles.
    

### 

[](#base-url)

Base URL

The base URL for API requests is defined as {{base-url}}. Replace this variable with the appropriate environment URL (e.g., https://api.xpresswallet.com for production or a sandbox URL).

The Third party generic api requires api key.

[Request API Key](/quick-start)

**Base Url:** [https://api.xpresswallet.com](https://api.xpresswallet.com/)

Scripts

```
if (pm.response.code === 200 || pm.response.code === 201 || pm.response.code === 400 || pm.response.code === 403) {

    const accessToken = pm.response.headers.get("X-Access-Token")
    const refreshToken = pm.response.headers.get("X-Refresh-Token")

    if (accessToken) {
        pm.environment.set("access-token", accessToken);
    }

    if (refreshToken) {
        pm.environment.set("refresh-token", refreshToken);
    }
}
```

* * *

### 

[](#base-url-1)

Base URL

All endpoints are relative to the base URL:

```
{{base-url}}
```

### 

[](#authentication)

Authentication

Most endpoints require authentication via `X-Access-Token` and `X-Refresh-Token` headers. Some endpoints also use a Bearer Token for authorization.

**Headers**:

```
{
  "X-Access-Token": "{{access-token}}",
  "X-Refresh-Token": "{{refresh-token}}"
}
```

For endpoints requiring Bearer Token:

```
{
  "Authorization": "Bearer {{vault:authorization-secret}}"
}
```

[PreviousNIPFundTransferMultipleDebitAccounts](/third-party-generic-api/nipfundtransfermultipledebitaccounts)[NextAuthentication](/xpress-wallet-api/authentication)