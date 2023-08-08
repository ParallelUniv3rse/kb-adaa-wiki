# Implementation guide

- describe how to implement your app, which screen you need implement
- [demo app](https://api.kb.cz/adaa-flow/)

## Actors

- Client KB - User who give access to his account via API in Komercni banka
- Developer - Developer who create app
- Bank - Komercni banka

## Flow

### 1. Developer register on [production API portal](https://api.kb.cz/open/apim/store/site/pages/login.jag?requestedPage=/store/)

- create app
- subcribe to API (Client Registration, OAuth2, Adaa API)
- create API key (apiKey)

### 2. Developer calls [Software Statement](./Software-Statements#request)

### 3. Developer calls [Application Registration OAuth2](./Application-Registration-OAuth2#request) in browser

- browser shows this [page](https://api.kb.cz/adaa-flow/disclaimer.html)  and gives control to Bank

### 4. Client KB works in Bank - Register app

- Client KB continue to [login](https://api.kb.cz/adaa-flow/login2.html) to bank
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

### 9. Developer calls - Accounts

- [Accounts](./Accounts) for  account id to next step

## How prolong tokens?

- after expiration refesh token, you can call [authirozation](./Tokens#authorization-code) to get new refresh token for next 12 months
