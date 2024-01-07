# Migration guide

Migration guide from the old api portal (https://api.kb.cz) to the new api portal (https://developers.kb.cz).

## General changes
- Api key header is now mandatory and renamed from `x-api-key` to `apiKey`.
- Each api now has its own apiKey. They cannot be reused between different API's. Generate new apiKeys in the API portal and replace them in your app.
- Always fill the `apiKey` header without the "Bearer" prefix.

<br/>

<details><summary> Instructions for API business suite (ADAA - Account direct Access API)</summary>

## 1. Login into the new API portal

- Login to <https://developers.kb.cz> - you can use the username and password from the old API portal.

## 2. New Software statements v2

> **IF YOU HAVE ALREADY REGISTERED YOUR APP IN THE OLD API PORTAL, YOU DON'T NEED TO REGISTER IT AGAIN IN THE NEW API PORTAL.** \
> You can safely skip step 2.

- URL has changed: <https://client-registration.api-gateway.kb.cz/v2>.
- v1 will be operational until 31.1.2024.

## 3. _Client_ Application registration

> **IF YOU ALREADY HAVE A _CLIENT_ REGISTRATION (`client_id` and `client_secret`) FOR YOUR USER, YOU DON'T NEED TO RE-REGISTER THEM AGAIN.** \
> You can safely skip step 3.

- URL has changed: <https://api-gateway.kb.cz/client-registration-ui/v1/saml/>

## 4. Authenticate your requests via the new Oauth2 v2 API

- URL has changed: <https://api-gateway.kb.cz/oauth2/v2>.
- v1 will be operational until 31.1.2024.

## 5. Account direct access v1

- URL has changed: <https://api-gateway.kb.cz/adaa/v1>.
- Remove usages of the `/account-ids` endpoint → it has been replaced replaced by `/accounts`
  - The `/account-ids` endpoint will be operational until 31.1.2024.

</details>

<br />

<details><summary>Instructions for other APIs (Exchange Rates, Branches and ATMs, Contact Requests, etc.)</summary>

## 1. Login into the new API portal

- Login to <https://developers.kb.cz> - you can use the username and password from the old API portal.

## 2. Open the API page and create a new apiKey

## 3. Replace the apiKey in your app

## 4. Replace the old URL with the new one

![atm](./img/atm-detail.min.png)
</details>
