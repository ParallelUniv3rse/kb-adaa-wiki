# Transaction history

- API is able to return data for up to 2 years back
- If you don't fill in the `fromDate` and `toDate` parameters, the transaction history is returned only the last 90 days.
- **ONLY** use the `accountServicer` attribute as the unique payment identifier. This will provide you with a stable, non-changing unique identifier throughout the entire payment lifecycle.

> **Limits**
>
> - Timeout to start downloading the next page is 10s.
> - Reading transaction history is limited to once per hour. If you want to read history sooner when something changes, try [Account Update Notifications](./08-Account-Update-Notifications)

## Request

```json
curl --location --request GET 'https://api-gateway.kb.cz/adaa/v1/accounts/Zm9PTlRTeFppV3N3eERxOUVueEE2Y2xYUU5NbGg3NSthUktwUzhzcGE5MW42USs1cmlUbWZGNkM2aXp1MDROaE1sV2p5UDVlbEdxYWxFejRtdkNqQ1E9PQ/transactions?fromDate=2022-01-15&toDate=2022-03-05&size=20&page=0' \
--header 'x-correlation-id: 6d745f4e-eb52-441a-a1e3-86f82619ab83' \
--header 'apiKey: 3a7f779a-8cc1-364f-be2b-9ea161f63817' \
--header 'Authorization: Bearer eyJ0eXAiOiJKV1QiLCJraWQiOiJ3RjJTa1I3NWMxamZsZ1VIOWJ6Wno3Tzllemc9IiwiYWxnIjoiUlMyNTYifQ.eyJzdWIiOiJBUElJRD01MmYwNDgyNjM3OTM0ZGZmOWY5MjE1MTBhMjlhMWYwYSIsImN0cyI6Ik9BVVRIMl9TVEFURUxFU1NfR1JBTlQiLCJhdXRoX2xldmVsIjo2LCJhdWRpdFRyYWNraW5nSWQiOiIwN2UyZjk4NC0zNTJjLTQ1ZmItYTk5MC0yOGEzZTI3NDA2MmUtMzE4OTk5MTUiLCJpc3MiOiJodHRwczovL2NhYXMua2IuY3ovb3BlbmFtL29hdXRoMiIsInRva2VuTmFtZSI6ImFjY2Vzc190b2tlbiIsInRva2VuX3R5cGUiOiJCZWFyZXIiLCJhdXRoR3JhbnRJZCI6IjF1bzJ1ZHNjS0dLSWQwVjFFT2ZzRW1sUUtQcyIsImF1ZCI6IktpZmxpLTE2MzUiLCJuYmYiOjE2NTU3MzA3MzAsImdyYW50X3R5cGUiOiJyZWZyZXNoX3Rva2VuIiwic2NvcGUiOlsiYWRhYSJdLCJhdXRoX3RpbWUiOjE2NTUzNzcyNzMsInJlYWxtIjoiLyIsImV4cCI6MTY1NTczMDkxMCwiaWF0IjoxNjU1NzMwNzMwLCJleHBpcmVzX2luIjoxODAsImp0aSI6InJWZERFQktFR2dMbjVCQk9RTjRIY3F5Y1k4YyIsImNhYXNPcGVyYXRpb25JZCI6IjUyNzYyMTc3NmRiODQ0MTg5MGJjM2MzM2RkZjYzYmVlIn0.r26PDIs4uuVGrmECIkQqM16lDL2a-XEWvfJOqMJVA8zHfFEDmLQ3VRj4nOiXjfp4uwQQUVTSzYaMkNw4BGsCtxRRvk54pFgCcl8GtSlfhL44cMA3mtZuEx39tqsdndymvPE6U9-wP5nzzeFJdZsOeAbzAGgIwWTNcUSH6YlbQLkuH-Z4qVnVCVwwspzEupJsgnRGYuDVzhk0BP4eDzF12fdRx7Zq2cCGY0H89XwWrf7GBpZQubzZgACle8r1oOR86_65Wwd88oNo5HUfC_kKGyYL-lhMIGbcbMGf5SX1Te7PPBAy9q2BQnRhcpIunvGKSv_aAiFOW9DMLWgUT6vPhA'
```

## Response

```json
{
  "content": [
    {
      "lastUpdated": "2022-06-16T11:10:00.336259Z",
      "accountType": "KB",
      "entryReference": "120-20210222 T02AR0H7AB803",
      "iban": "CZ0301000001158830140287",
      "creditDebitIndicator": "CREDIT",
      "transactionType": "DOMESTIC",
      "bankTransactionCode": {
        "code": "10000107000",
        "issuer": "CBA"
      },
      "amount": {
        "value": 4000.0,
        "currency": "CZK"
      },
      "bookingDate": "2021-02-23",
      "valueDate": "2021-02-23",
      "instructed": {
        "value": 4000.0,
        "currency": "CZK"
      },
      "status": "BOOK",
      "counterParty": {
        "iban": "CZ2962106701002201598706",
        "name": "KATERINA SONTAKOVA",
        "accountNo": "6701002201598706",
        "bankBic": "BREXCZPPXXX",
        "bankCode": "6210"
      },
      "references": {
        "accountServicer": "311892adb7f2b601",
        "receiver": "PLATBA"
      },
      "additionalTransactionInformation": "Ach deposit"
    },
    {
      "lastUpdated": "2022-06-16T11:10:00.336282Z",
      "accountType": "KB",
      "entryReference": "205-26022021 1086000939773",
      "iban": "CZ0301000001158830140287",
      "creditDebitIndicator": "DEBIT",
      "transactionType": "CARD",
      "bankTransactionCode": {
        "code": "30000201330",
        "issuer": "CBA"
      },
      "amount": {
        "value": 2672.0,
        "currency": "CZK"
      },
      "bookingDate": "2021-02-26",
      "valueDate": "2021-02-23",
      "instructed": {
        "value": 2672.0,
        "currency": "CZK"
      },
      "status": "BOOK",
      "counterParty": {
        "name": "HM.COM"
      },
      "references": {
        "accountServicer": "81ea35a30bb7d013",
        "variable": "10128905",
        "constant": "1178",
        "specific": "102123001",
        "receiver": "HM.COM 800040464 CZ 30 4917 79** **** 3844 VISA 23.02.2021 2.672,00 CZK"
      }
    },
    {
      "lastUpdated": "2022-06-16T11:10:00.336367Z",
      "accountType": "KB",
      "entryReference": "362-02042021 1602 602105 100070",
      "iban": "CZ0301000001158830140287",
      "creditDebitIndicator": "DEBIT",
      "transactionType": "DOMESTIC",
      "bankTransactionCode": {
        "code": "10000108000",
        "issuer": "CBA"
      },
      "amount": {
        "value": 2000.0,
        "currency": "CZK"
      },
      "bookingDate": "2021-04-04",
      "valueDate": "2021-04-04",
      "instructed": {
        "value": 2000.0,
        "currency": "CZK"
      },
      "status": "BOOK",
      "counterParty": {
        "iban": "CZ0208000000002795161113",
        "accountNo": "0000002795161113",
        "bankBic": "GIBACZPXXXX",
        "bankCode": "0800"
      },
      "references": {
        "accountServicer": "2a298af7ee51cdff"
      },
      "additionalTransactionInformation": "Force pay debit, OI00014M3AZ"
    }
  ],
  "totalPages": 3,
  "pageNumber": 0,
  "pageSize": 20,
  "numberOfElements": 20,
  "first": true,
  "last": false,
  "empty": false
}
```

---

## Next step
[Continue to Account Update Notifications...](./08-Account-Update-Notifications)
