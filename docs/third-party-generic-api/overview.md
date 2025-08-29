# THIRD PARTY GENERIC API

The Third party generic api requires api key.

[Request API Key](/quick-start)

**Base Url:** [http://154.113.16.142:8882/postingrest](http://154.113.16.142:8882/postingrest)

* * *

The interface is implemented as a RESTful web service, exposing the following methods:

*   GetBVNDetails
    
*   GetNIPAccount
    
*   NIPFundTransfer
    
*   GetNipBank
    
*   ProvidusTransactionsStatus
    
*   ProvidusFundsTransfer
    
*   NIPFundTransferMultipleDebitAccounts
    

* * *

API Endpoints

### 

[](#get-nip-account)

Get NIP Account

Reserved accounts are static accounts assigned to a specific user. They do not expire, but should be used judiciously, as there is a limit to the number of virtual accounts that can be created.

[GetNIPAccount](/third-party-generic-api/getnipaccount)

* * *

### 

[](#create-dynamic-account)

Create Dynamic Account

_Dynamic accounts are designed for one-time payments and can be assigned to different users. By default, they expire 10 minutes after creation (this can be extended up to a maximum of 48 hours) before being reassigned to another user. They must be used for a single payment before expiration._

[Create Dynamic Account Number](/virtual-payment/create-dynamic-account-number)

* * *

### 

[](#update-account-name)

Update Account Name

_The /PiPUpdateAccountName endpoint is used exclusively for reserved accounts. It allows you to update the account name. In most cases, if a reserved account has been assigned to a user who does not utilize it for transactions, you can reassign the account to another user by updating the account name—helping you manage your limited pool of virtual accounts efficiently._

[Update Account Name](/digital-collection-service-dcs/update-account-name)

* * *

### 

[](#blacklist-whitelist-account)

Blacklist / Whitelist Account

_The /PiPBlacklistAccount endpoint is used when you suspect that a user is using an account for fraudulent transactions. To prevent funds transferred to such an account from eventually entering your settlement account, you can call this endpoint to blacklist the account._

_Please note that virtual accounts cannot be deleted—they can only be blacklisted using the /PiPBlacklistAccount endpoint. Also, blacklisted accounts can still receive funds; however, payment notifications will not be processed successfully until the blacklist flag is removed._

_To remove a blacklist (i.e., to whitelist an account), use the /PiPBlacklistAccount endpoint with the appropriate flag._

[Blacklist/Whitelist Account](/digital-collection-service-dcs/blacklist-whitelist-account)

* * *

### 

[](#verify-transaction-by-session-id)

Verify Transaction by Session ID

_The verification endpoints are used to confirm that transactions sent to your webhook originate from Providus Bank and to retrieve detailed information about those transactions._

_Typically, when our system sends a webhook notification, the fintech first calls the appropriate verification endpoint to validate the transaction before responding to the webhook._

_You can verify a transaction using either the Session ID or Settlement ID provided in the webhook request or previously shared with the fintech, to confirm the transaction exists on our system._

This endpoint is to verify a transaction by supplying the session id and credentials.

[Verify Transaction by Session ID](/digital-collection-service-dcs/verify-transaction-by-session-id)

* * *

### 

[](#verify-transaction-by-settlement-id)

Verify Transaction by Settlement ID

This endpoint is to verify a transaction by supplying the session id and credentials.

[Verify Transaction by Session ID](/digital-collection-service-dcs/verify-transaction-by-session-id)

* * *

### 

[](#fintech-webhook)

Fintech Webhook

Fintech Webhook Endpoint (Your system should expose this endpoint to receive notifications)

[Webhook Specification](/digital-collection-service-dcs/webhook-specification)

Notes

· Dynamic accounts expire after 10 minutes (configurable up to 48 hours).

· Reserved accounts do not expire but have a creation limit.

· Funds are swept to your settlement account only upon successful webhook acknowledgment.

· Duplicate settlement IDs must not be reprocessed.

· Blacklisted accounts can still receive funds, but no notifications will be sent until whitelisted.

[PreviousWebhook Specification](/digital-collection-service-dcs/webhook-specification)[NextGetNIPAccount](/third-party-generic-api/getnipaccount)