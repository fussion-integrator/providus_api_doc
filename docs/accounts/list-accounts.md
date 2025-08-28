# List Accounts

Retrieve a list of customer accounts.

## Endpoint

`GET /api/v1/accounts`

## Parameters

| Parameter | Type | Description |
|-----------|------|-------------|
| limit | integer | Number of accounts to return |
| offset | integer | Number of accounts to skip |

## Response

```json
{
  "accounts": [
    {
      "id": "12345",
      "name": "John Doe",
      "balance": 1000.00,
      "currency": "NGN"
    }
  ]
}
```