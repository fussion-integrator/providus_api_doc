# Welcome!

Welcome to ProvidusBank API Documentation. The platform provides explicit details on services exposed by the bank for use in developing your digital innovative products.

Here, you will find everything you need to get your first application off the ground, including some sample codes. This section is intended as a reference for those working with APIs for the first time, but it should also serve as a guide with references for common use cases. We recommend going through the various sections contained in this documentation in order to successfuly build your product.

Currently, each API is protected by either a token authentication type or an oauth authentication type.

### Accessing a token Protected API

To access a token Protected API follow the steps below :

- You need to subscribe to the API by requesting for an access token to the API.
- Access the token protected API by passing the token in an authorization header.

You need to subscribe to the API by requesting for an access token to the API.

Access the token protected API by passing the token in an authorization header.

### Accessing an Oauth Protected API :

To access an Oauth Protected API , you need to subscribe to the API by through the following steps :

- Request for an oauth clientRequest for an oauth client and API access token
- Request for an Authorization code using your oauth client by making an API call to the authorization URL of the API. You will be redirected to a login page to provide their credentials. On successful login, the authorization code will be made available at the redirect URL registered on the oauth client. Find documentation of this request any oauth protected API under the documentation of that API.
- Exchange authorization code for token by making an API call to the token URL of the API. Find documentation of this request any oauth protected API under the documentation of that API.
- Access the oauth API by passing the token in an authorization header.

Request for an oauth client

Request for an oauth client and API access token

Request for an Authorization code using your oauth client by making an API call to the authorization URL of the API. You will be redirected to a login page to provide their credentials. On successful login, the authorization code will be made available at the redirect URL registered on the oauth client. Find documentation of this request any oauth protected API under the documentation of that API.

Exchange authorization code for token by making an API call to the token URL of the API. Find documentation of this request any oauth protected API under the documentation of that API.

Access the oauth API by passing the token in an authorization header.

### Notes :

- The authentication url and token url can be found on the documentation for each API.
- Sample API calls in different languages are documented for each API below.

The authentication url and token url can be found on the documentation for each API.

Sample API calls in different languages are documented for each API below.

Test Base URL

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
https://api-staging.providusbank.com
```

### Production Base URL

```inline-grid min-w-full grid-cols-[auto_1fr] [count-reset:line] print:whitespace-pre-wrap
https://api.providusbank.com
```

The authentication url and token url can be found on the documentation for each API.

Note : Sample API calls in different languages are documented for each API below.

Last updated 4 months ago