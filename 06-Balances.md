# Balances

## Request Balances

```bash
curl --location --request GET 'https://api-gateway.kb.cz/adaa/v1/accounts/SU1iL3NaSmR1b3NYWEZLOTk2MG8rNVV6VzB4MzAvV3ExTWpHQVRmL2JNT2N3RWVCa0VXQVA3MnNabkJTc3BteldvNWNGT1U4U1VBbDREWXY1WlZMOGc9PQ/balances' \
--header 'x-correlation-id: 0595d8f5-c4be-4402-9d11-69dd934a7805' \
--header 'apiKey:  3a7f779a-8cc1-364f-be2b-9ea161f63817' \
--header 'Authorization: Bearer eyJ0eXAiOiJKV1QiLCJraWQiOiJ3RjJTa1I3NWMxamZsZ1VIOWJ6Wno3Tzllemc9IiwiYWxnIjoiUlMyNTYifQ.eyJzdWIiOiJBUElJRD01MmYwNDgyNjM3OTM0ZGZmOWY5MjE1MTBhMjlhMWYwYSIsImN0cyI6Ik9BVVRIMl9TVEFURUxFU1NfR1JBTlQiLCJhdXRoX2xldmVsIjo2LCJhdWRpdFRyYWNraW5nSWQiOiJlYmI0YTJmZS0yNjA3LTQ2OTUtOGU3Mi05OGU3Nzg5MmMwOGQtMjk5NjQ0MzEiLCJpc3MiOiJodHRwczovL2NhYXMua2IuY3ovb3BlbmFtL29hdXRoMiIsInRva2VuTmFtZSI6ImFjY2Vzc190b2tlbiIsInRva2VuX3R5cGUiOiJCZWFyZXIiLCJhdXRoR3JhbnRJZCI6IjF1bzJ1ZHNjS0dLSWQwVjFFT2ZzRW1sUUtQcyIsImF1ZCI6IktpZmxpLTE2MzUiLCJuYmYiOjE2NTUzNzc2MjAsImdyYW50X3R5cGUiOiJyZWZyZXNoX3Rva2VuIiwic2NvcGUiOlsiYWRhYSJdLCJhdXRoX3RpbWUiOjE2NTUzNzcyNzMsInJlYWxtIjoiLyIsImV4cCI6MTY1NTM3NzgwMCwiaWF0IjoxNjU1Mzc3NjIwLCJleHBpcmVzX2luIjoxODAsImp0aSI6IkludkM0TWRNYkw2aEVHbU16NVRHaTBNSnVmZyIsImNhYXNPcGVyYXRpb25JZCI6IjUyNzYyMTc3NmRiODQ0MTg5MGJjM2MzM2RkZjYzYmVlIn0.iHa9qv-sXNvAaBRMH-gPT6c554sLkKmwOouQ6z7rmjv1J3uhppDsyE9GPex-N5bUMX7qCJZuzVap4nUtR5FBXhrCBAl3LjnAc1qvB3SmG79s9VlK7khAOn4YIdmspQ5QoytTTebuDazAQd5GoXFKnnOyxbsfglhjQbH6lM9A-v_vL9WNwnmAq1Wra2U7S0iLzdkGr3gMKszT5sFAk3T1nC5fxrwZBCAsk5JR9Cy4mrPATNtpHqPiPphvFtj3ahg4fvw_ZBD_zl3Do-gbsDvgbij30mIa9DY6F89MqKS-HPI11KjbniJ0M1fPj2RUMzsMKVFn-UA6QZqZj2ArKXPB9Q'
```

## Response Balances

```json
[
  {
    "type": "CLOSING_AVAILABLE",
    "creditDebitIndicator": "CREDIT",
    "amount": {
      "value": 85061.41,
      "currency": "CZK"
    },
    "validAt": "2022-06-16T11:07:03.156Z",
    "creditLine": {
      "value": 0.0,
      "currency": "CZK"
    }
  },
  {
    "type": "PREVIOUSLY_CLOSED_BOOK",
    "creditDebitIndicator": "CREDIT",
    "amount": {
      "value": 85061.41,
      "currency": "CZK"
    },
    "validAt": "2022-06-16T11:07:03.156Z",
    "creditLine": {
      "value": 0.0,
      "currency": "CZK"
    }
  }
]
```

---

## Next step
[Continue to Transaction...](./07-Transactions)
