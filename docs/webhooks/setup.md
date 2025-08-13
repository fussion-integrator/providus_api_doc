# Webhook Setup

Learn how to configure and handle webhooks from ProvidusBank.

## Configuration

1. Log into your developer dashboard
2. Navigate to Webhooks section
3. Add your endpoint URL
4. Select event types

## Handling Webhooks

```javascript
app.post('/webhook', (req, res) => {
  const event = req.body;
  
  switch(event.type) {
    case 'payment.completed':
      // Handle successful payment
      break;
    case 'payment.failed':
      // Handle failed payment
      break;
  }
  
  res.status(200).send('OK');
});
```
