# Product

The Account Direct Access API (ADAA) service provides secure access to information about:

- Client’s transaction history
- Bank account balance
- Information about transaction history is provided in connection with current accounts of a client of Komerční banka.

more details is on website [Direct Account Access API](https://www.kb.cz/cs/kbapi/sluzby-kb-api/primy-pristup-k-uctu)

## Enviroments

- For testing requests we recommend the application [Postman](https://www.postman.com)

### Sandbox

- Postman [Sandbox](./postman/KB%20API%20-%20Sandbox%20-%20Direct%20access%20to%20account%20.postman_collection.json) collection
- Register on [Sandbox API Portal](https://api.kb.cz/open/apim/store/site/pages/login.jag?requestedPage=/store/)

### Production

- Postman [Production](./postman/KB API - Production - API Business suite.postman_collection.json) collection
- Register on [production API portal](https://api.kb.cz/open/apim/store/site/pages/login.jag?requestedPage=/store/)

## How to start

- [swagger](https://github.com/komercka/adaa-client/blob/master/api/src/main/resources/openapi/adaa-api-v1.json)
- [demo app](https://api.kb.cz/adaa-flow/)

### Process

![Process flow](./img/flow.min.png)

### Actors

- User - Client KB - User who give access to his account via API in Komercni banka
- Developer - Developer who create app
- KB - Komercni banka

### 1. Developer registers on [production API portal](https://api.kb.cz/open/apim/store/site/pages/login.jag?requestedPage=/store/)

- create application
- subcribe to API (Client Registration, OAuth2, Adaa API)
- create API key (apiKey)

<details><summary>how create API key (apiKey)</summary>

![api portal - api key](./img/api-key.min.png)

</details>

### 2. Developer registers your application in KB

- [Software Statement](./Software-Statements) with qualified certificate issued by a trusted certification authority (I.CA, PostSignum)

### 3. Developer calls [Application Registration OAuth2](./Application-Registration-OAuth2#request) in browser

- browser shows this [page](https://api.kb.cz/adaa-flow/disclaimer.html) and gives control to KB

### 4. Client KB works in Bank - Register app

- Client KB continue to [login](https://api.kb.cz/adaa-flow/login.html) to bank
- [Authorize app](https://api.kb.cz/adaa-flow/klic-aplikace.html)
- Client KB [choose accounts](https://api.kb.cz/adaa-flow/vyber-uctu.html) to API
- Bank transfer control back to app

### 5. Developer processes the application registration information

- [decrypt](./Application-Registration-OAuth2#decrypt-response)  on redirect_uri, you registered in [Software Statement](./Software-Statements#request), we give you link to decrypt client_id, client_secret, [application registration](./Application-Registration-OAuth2)

### 6. Developer calls - Authorization code [Tokens](./Tokens#authorization-code)

### 7. Client KB works in Bank - Confirm apps scopes

- Client KB continue to [login](https://api.kb.cz/adaa-flow/login2.html) to bank
- Client KB [confirms scopes](https://api.kb.cz/adaa-flow/klic-ucty.html)
- Bank transfer control back to app

### 8. Developer processes authorization code

- [change authorization code](./Tokens#response-authorization-code) to refresh token and access token

### 9. Developer get - Accounts

- [Accounts](./Accounts) for  account id to next step

### Next endpoints

5. [Account Balances](./Balances)
6. [Transactions](./Transactions)
7. [Notification of changes to your account (webhook)](./Notification)
8. [Account Statements - PDF](./Statements-PDF)

## Recommendations for the user interface

- support for flow registration of the application by the user (each user needs only 1 application)
- support for token acquisition and renewal (once every 12 months or sooner)
- our [demo app](https://api.kb.cz/adaa-flow/)
