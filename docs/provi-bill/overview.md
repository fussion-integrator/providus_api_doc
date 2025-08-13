# Provi Bill

Payment APIs provide interfaces to create and manage financial Payments. The interface provides the following methods:

This document provides a comprehensive guide to the Provibill Test Public API, which allows users to manage bill payments, including retrieving categories, bills, fields, validating customer details, making payments, and inquiring about payment status. Each endpoint is detailed with its HTTP method, URL, authentication requirements, and code samples in cURL, Python, Java, JavaScript, PHP, C#, and Dart.

### Base URL

All endpoints are relative to the base URL:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
http://154.113.16.142:9999/provipay/webapi
```

### Authentication

All endpoints require Basic Authentication using a username and password.

**Basic Authentication**Headers:

**Headers**```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
Authorization: Basic <base64-encoded-username:password>
```

To generate the Basic Auth header, encode the username:password string in Base64. For example, if the username is user and the password is pass, the header would be:

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
Authorization: Basic dXNlcjpwYXNz
```

Last updated 9 days ago