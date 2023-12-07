# How to move to the new KB API portal

- We migrate to the new API portal. The new portal is available at <https://developers.kb.cz>.
- Users and password are migrated to new portal
- Old portal <https://api.kb.cz> wil be available until 31.01.2024.
- Sandboxes are now on the same portal as production services

## Change for all services

- We recommend updating the URL from <https://api.kb.cz/open/api/service/v1> to <https://api-gateway.kb.cz/service/v1>
  - (for example, <https://api.kb.cz/open/api/adaa/v1> to <https://api-gateway.kb.cz/adaa/v1>
  - The old ones will be functional until 31.1.2024, after which they will be turned off
- Rename the header apiKey to apiKey.

## 1. Login in the new API portal

- login to portal <https://developers.kb.cz>
- subscribe to the API you need to use ADAA
  - Client Registration v2
  - Oauth2 v2
  - Account direct access v1
- each API must have its own API key (we have cancelled the applications)

## 2. New Client registration v2

- Mandatory
  - Rename the header apiKey to apiKey
  - secton contacts.email
- New url: <https://client-registration.api-gateway.kb.cz/v2>
- v1 will be operational until 31.1.2024

## 3. New OAuth2 v2

- Mandatory and rename the header apiKey to apiKey
- New url: <https://api-gateway.kb.cz/oauth2/v2>
- v1 will be operational until 31.1.2024

## 4. Account direct access v1

- Rename the header apiKey to apiKey
- New url: <https://api-gateway.kb.cz/adaa/v1>
- Terminate the endpoint /account-ids → replaced by /accounts
  - the endpoint /account-ids will be operational until 31.1.2024
