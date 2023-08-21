# TODO List for Developers  - Migration to the new API portal

## 1. Migration to the new API portal

- Create a new Application/Project in the new API portal
  - [ ] Create a new Application/Project in the new API portal
  - [ ] Create a new API key
  - [ ] Replace the API key in the application
- subscribe to the API you need to use ADAA
    - Oauth2 v2
    - Client Registration v2
    - ADAA v1
- generate a new API key. → Replace the key in the application

## 2.  Change for all services

- We recommend updating the URL from <https://api.kb.cz/open/api/service/v1> to <https://api-gateway.kb.cz/service/v1> 
    - (for example, <https://api.kb.cz/open/api/adaa/v1> to <https://api-gateway.kb.cz/adaa/v1>
  - The old ones will be functional for another x months, after which they will be turned off
- Rename the header x-api-key to apiKey.

## 3.  New OAuth2 v2 - 

- Mandatory attribute apiKey
- 
- v1 will be operational for the next x months

### 1.3. Termination of the API ADAA endpoint /account-ids -> /accounts

- [ ] Terminate the endpoint /account-ids → replaced by /accounts
  - the endpoint /account-ids will be operational for another 3 months

### 1.4. Moving sandboxes to the new API portal

- [ ] Sandboxes are now on the same portal as production services
