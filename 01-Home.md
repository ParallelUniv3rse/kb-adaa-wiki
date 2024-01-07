# Product

The Account Direct Access API (ADAA) service provides secure access to information about:

- Client’s transaction history
- Bank account balance
- Information about transaction history is provided in connection with current accounts of a client of Komerční banka.

You can find more details on the [Direct Account Access API](https://www.kb.cz/cs/kbapi/sluzby-kb-api/primy-pristup-k-uctu) website.

## Enviroments

For testing and debugging your requests we recommend to use the [Postman](https://www.postman.com) app.
We have prepared collections of example requests to use in Postman, download them from the links below.

### Sandbox

- Postman [Sandbox](./postman/KB-API-Sandbox-API-Business-suite.postman_collection.json) collection

### Production

- Postman [Production](./postman/KB-API-Production-API-Business-suite.postman_collection.json) collection

## How to start

Useful links:
- [API documentation in Swagger](https://github.com/komercka/adaa-client/blob/master/api/src/main/resources/openapi/adaa-api-v1.json)
- [Demo app](https://api.kb.cz/adaa-flow/)

### Actors

- User - _Client of KB_ - User who grants access to their account in Komercni banka
- _Developer_ - Developer who creates an application that will use the API
- _KB_ - Komercni banka

### Process

Reference diagram of the request-response flow:
![Process flow](./img/flow.min.png)

### 1. Register on KB API portal

To use any of our API's you (the _Developer_) will need to be registred on our API portal. Though the API portal you will be able to subscribe to the API's you want to use and generate API keys.

- Register on the [API Portal](https://developers.kb.cz)

### 2. Create API keys for the API's you will be using

- Subcribe to an API (Client Registration, OAuth2, Account direct access API)
- create an API key for it (apiKey) - [How create API key (apiKey)](https://developers.kb.cz/manual#apikey)

Each API needs its own API key. You can create multiple API keys for each API. You can also create multiple API keys for the same API.

### 3. Register your application via the Client Registration API

Create a Software statement for your application and register it via the Client Registration API. You will need to use the API key you created in the previous step.

- [Software Statement](./02-Software-Statements) with qualified certificate issued by a trusted certification authority (I.CA, PostSignum)

You will get a JWT token with details about your application. You will need to use this token in the next step.

### 4. Construct a URL to the Application Registration endpoint and visit it in the _Client_'s browser.

- Construct a URL as described in the [Application Registration OAuth2](03-Application-Registration-OAuth2#request).
- Visit the constructed URL in the _Client_'s browser.
- Browser redirects to _KB_ for an authorization of a _Client of KB_. ([example page](https://api.kb.cz/adaa-flow/disclaimer.html))

### 5. _Client of KB_ registers an app connection inside _KB_'s interface

- _Client of KB_ continues to login to _KB_. ([example page](https://api.kb.cz/adaa-flow/login.html))
- _Client of KB_ confirms authorization via an authorization app (KB Klíč). ([example page](https://api.kb.cz/adaa-flow/klic-aplikace.html))
- _Client of KB_ chooses accounts to be authorized with the API. ([example page](https://api.kb.cz/adaa-flow/vyber-uctu.html))
- _KB_ redirects back to a callback url provided in the software statement and that way transfers control back to the app.

### 6. Decrypt the application registration information

You, the _Developer_, needs to process the information included in the callback URL. 

- [Decrypt](./03-Application-Registration-OAuth2#decrypt-response) the parameters on the redirect_uri
- obtain the `client_id`, `client_secret`, and other [application registration](./03-Application-Registration-OAuth2) information from the decrypted data.

You will need the `client_id`, `client_secret` in the next steps.

### 7. Construct a URL to get the [Authorization code Token](./04-Tokens#authorization-code) and visit it in the _Client_'s browser.

Using the client_id obtained in the previous step, construct a URL to get the authorization code token.

- Construct a URL as described in the [Tokens - Authorization code wiki page](./04-Tokens#authorization-code).
- Visit the constructed URL in the _Client_'s browser.
- Browser redirects to _KB_ for an authorization of a _Client of KB_. ([example page](https://api.kb.cz/adaa-flow/disclaimer.html))


### 8. _Client of KB_ confirms app scopes inside _KB_'s interface

- _Client of KB_ continues to login to _KB_. ([example page](https://api.kb.cz/adaa-flow/login2.html))
- _Client of KB_ confirms scopes ([example page]((https://api.kb.cz/adaa-flow/klic-ucty.html)))
- _KB_ redirects back to a callback url provided in the request URL parameter and that way transfers control back to the app.

### 9. Obtain Refresh token and Access Token using the Authorization code

You, the _Developer_, needs to process the information included in the callback URL.

- Get the Authorization code from the callback URL's parameters
- Use the Authorization code , `client_id` and `client_secret` to get the [Refresh token and Access Token](./04-Tokens#response-authorization-code)

### 10. Call the ADAA API using the Access token provided

- First, you will probably want to get the _Client_'s [Accounts](./05-Accounts) available. The `accountId` is needed for other endpoints.

[Account Balances](./06-Balances) \
[Transactions](./07-Transactions) \
[Notification of changes to _Client_'s account (webhook)](./08-Account-Update-Notifications) \
[Account Statements - PDF](./09-PDF-Statements)

## Recommendations for your App's user interface:

- Make a flow to create an Application Registration by the user (step 4) - each user needs only 1 application
- Make a flow for Refresh token acquisition and renewal (step 7) - once every 12 months or sooner. Refresh token is valid for 12 months.
- Check out our [demo app](https://api.kb.cz/adaa-flow/)
