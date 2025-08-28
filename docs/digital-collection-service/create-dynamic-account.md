1. Digital Collection Service (DCS)

# Create Dynamic Account

Dynamic accounts are for one-time payments and can be reassigned. They expire 10 minutes after creation by default (extendable up to 48 hours).

Dynamic accounts are designed for one-time payments and can be assigned to different users. By default, they expire 10 minutes after creation (this can be extended up to a maximum of 48 hours) before being reassigned to another user. They must be used for a single payment before expiration.

*Dynamic accounts are designed for one-time payments and can be assigned to different users. By default, they expire 10 minutes after creation (this can be extended up to a maximum of 48 hours) before being reassigned to another user. They must be used for a single payment before expiration.*#### Production Base URL

http://154.113.16.142:8088/appdevapi/api/

#### HTTP Request

POST /PiPCreateDynamicAccountNumber

Post http://154.113.16.142:8088/appdevapi/api/PiPCreateDnamicAccountNumber

Request (Auto-gen Reference)

**Request (Auto-gen Reference)**```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
  "account_name": "lemuel"
}

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
  "account_number": "9978012701",
  "account_name": "lemuel",
  "requestSuccessful": true,
  "responseMessage": "OPERATION SUCCESSFUL",
  "responseCode": "00",
  "initiationTranRef": "Prov2312"
}

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
{
"requestSuccessful": false,
"responseMessage": "Error Completing Operation",
"responseCode": "03",
"initiationTranRef": ""
}

### Sample Implementation

Coming soon...