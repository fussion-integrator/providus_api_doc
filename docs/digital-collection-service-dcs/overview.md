# Digital Collection Service (DCS)

#### 

[](#how-the-dcs-system-works)

How the DCS System Works

*   **Use Case**: Customers have virtual wallets on your platform. To fund a wallet, you create a virtual account via the API and share its details with the customer. The customer transfers funds to this account.
    
*   **Process**:
    
    1.  Funds arrive in the virtual account.
        
    2.  DCS sends a transaction notification to your webhook.
        
    3.  Your webhook validates the account, settlement ID, and X-Auth-Signature.
        
    4.  Upon successful validation, funds are swept to your settlement account, and you credit the customer’s wallet.
        
    

#### 

[](#transaction-flow)

Transaction Flow

1.  User initiates a payment request.
    
2.  You call the DCS API to create a virtual account and link it to the user.
    
3.  User transfers funds to the virtual account.
    
4.  Upon receiving funds:
    
    *   If the account is dynamic and expired, the notification is logged as failed.
        
    *   If the account is dynamic and active or reserved, a notification is sent to your webhook.
        
    
5.  Your webhook responds:
    
    *   **Success**: Funds are swept to the settlement account.
        
    *   **Rejected**: Notification is logged as failed.
        
    *   **Error/No Response**: DCS retries up to 4 times; if unsuccessful, the notification is marked as pending.
        
    

#### 

[](#objectives)

Objectives

This API allows you to:

*   Generate virtual accounts (dynamic or reserved).
    
*   Handle webhook notifications.
    
*   Verify transaction details.
    
*   Manage account lifecycle (update, blacklist).
    

The Digital Collection Service requires a authentication header as stated below.

[Request API Key](/quick-start)

**Base Url:** http://154.113.16.142:8088/appdevapi/api/

* * *

### 

[](#authentication)

Authentication

#### 

[](#required-headers)

Required Headers

*   **Client-Id**: dGVzdF9Qcm92aWR1cw==
    
*   **X-Auth-Signature**: BE09BEE831CF262226B426E39BD109f2AF84DC63076D4174FAC78A2261F9A3D6E59744983B8326B69CDF2963FE314DFC89635CFA37A40596508DD6EAAB09402C7
    
*   **ClientSecret** (used for generating X-Auth-Signature): 29A492021F4B709A8D1152C3EF4D32DC5A7092723ECAC4C511781003584B48873CCBFEBDEAE89CF22ED1CB1A836213549BC6638A3B563CA7FC009BEB3BC30CF8 Signature is generated as <SHA512(Client-Id:ClientSecret)>.
    

* * *

API Endpoints

### 

[](#create-reserved-account)

Create Reserved Account

Reserved accounts are static accounts assigned to a specific user. They do not expire, but should be used judiciously, as there is a limit to the number of virtual accounts that can be created.

[Create Reserved Account](/digital-collection-service-dcs/create-reserved-account)

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

[PreviousBlacklist Account](/virtual-payment/blacklist-account)[NextCreate Reserved Account](/digital-collection-service-dcs/create-reserved-account)

Last updated 1 month ago