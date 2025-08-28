# Create Transaction

Process a new payment transaction.

## Endpoint

`POST /api/v1/transactions`

## Request Body

```json
{
  "amount": 1000.00,
  "currency": "NGN",
  "description": "Payment for services",
  "customer_id": "12345"
}
```

## Response

```json
{
  "transaction_id": "txn_67890",
  "status": "pending",
  "amount": 1000.00,
  "currency": "NGN"
}
```