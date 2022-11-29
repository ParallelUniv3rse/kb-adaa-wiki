# Product

The Account Direct Access API (ADAA) service provides secure access to information about:

- Client’s transaction history
- Bank account balance
- Information about transaction history is provided in connection with current accounts of a client of Komerční banka.

more details is on website [Direct Account Access API](https://www.kb.cz/en/kb-api/kb-api-services/account-direct-access)

## Enviroments

- For testing requests we recommend the application [Postman](https://www.postman.com)

### Sandbox

- Postman [Sandbox](./postman/KB%20API%20-%20Sandbox%20-%20Direct%20access%20to%20account%20.postman_collection.json) collection
- Register on [Sandbox API Portal](https://openbanking.kbcloud.cz/)

### Production

-  Postman [Production](./postman/KB%20API%20-%20Production%20-%20Direct%20access%20to%20account.postman_collection.json) collection
- Register on [production API portal](https://api.kb.cz/open/apim/store/site/pages/login.jag?requestedPage=/store/)

## How to start

### Register your application

1. [Software Statement](./Software-Statements)

### Client registration your application in bank

2. [Application Registration OAuth2](./Application-Registration-OAuth2)
3. [Tokens](./Tokens)

### Account and transaction history - [Swagger](https://github.com/komercka/adaa-client/blob/master/api/src/main/resources/openapi/adaa-api-v1.json)

4. [Accounts](./Accounts)
5. [Account Balances](./Balances)
6. [Transactions](./Transactions)
7. [Notification of changes to your account (webhook)](./Notification)
8. [Account Statements - PDF](./Statements-PDF)