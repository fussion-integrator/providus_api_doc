1. Transactions

# Get API authorization code for transaction

## Request Body

```json
{
  "redirect_uri": "\"redirect_uri_value\""
}
```

### Parameters

| Parameter | Type | Description |
|-----------|------|--------------|
| redirect_uri | string | The OAuth client redirect URI ( must be URL encoded ) |

Get an authorization code for the Transaction API.

#### Test Base URL

https://api-staging.providusbank.com

#### Production Base URL

https://api.providusbank.com

#### HTTP Request

`GET /transaction/oauth/authorize/`## Authorization Code.

`GET``https://api-staging.providusbank.com/v1 /account/NIP`Get API authorization code for transaction.

#### Headers

Content-Type

String

Request content type ( application/x-www-form-urlencoded )

#### Request Body

response_type*

String

`code`client_id

String

The OAuth client id



### Sample Implementation

Coming soon...

