# What you need to do

<details><summary> Instructions for API business suite (ADAA - Account direct Access API)</summary>

## 1. Login in the new API portal

- Login to portal <https://developers.kb.cz> - you can use username and password from the old API Portal.

## 2. New Client registration (Software statements) v2

- Api key header is mandatory and renamed from `x-api-key` to `apiKey`.
- Now each api has its own apiKey. It cannot be used for other API.
- Generate new apiKey and put your app. Fill header (apiKey) without "Bearer" prefix.
- The section contacts.email in the "body" part of the request is mandatory
- New url: <https://client-registration.api-gateway.kb.cz/v2>.
- v1 will be operational until 31.1.2024.

## 3. Registration OAuth2 client

- New url: <https://api-gateway.kb.cz/client-registration-ui/v1/saml/>

## 4. Authenticate your requests via the new Oauth2 v2 API

- Api key header is mandatory and renamed from `x-api-key` to `apiKey`.
- Now each api has its own apiKey. It cannot be used for other API.
- Generate new apiKey and put your app. Fill header (apiKey) without "Bearer" prefix.
- New url: <https://api-gateway.kb.cz/oauth2/v2>.
- v1 will be operational until 31.1.2024.

## 5. Account direct access v1

- Api key header renamed from `x-api-key` to `apiKey`
- Now each api has its own apiKey. It cannot be used for other API.
- Generate new apiKey and put your app. Fill header (apiKey) without "Bearer" prefix.
- New url: <https://api-gateway.kb.cz/adaa/v1>.
- Terminate the endpoint /account-ids → replaced by /accounts,
  - the endpoint /account-ids will be operational until 31.1.2024.

</details>

<details><summary>Instructions for other APIs (Exchange Rates, Branches and ATMs, Contact Requests, etc.)</summary>

## 1. Login in the new API portal

- Login to portal <https://developers.kb.cz> - you can use username and password from the old API Portal.

## 2. Open API and create apiKey

- Rename the header x-api-key to apiKey ("x-api-key" will no longer work).
- Generate new apiKey and replace it in your app. Fill header without "Bearer" prefix.
- Copy new url (replace old one in your app).

![atm](./img/atm-detail.min.png)
</details>
