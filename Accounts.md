# Accounts

## Request Accounts

```bash
curl --location --request GET 'https://api-gateway.kb.cz/adaa/v1/accounts' \
--header 'x-correlation-id: 9f1670dd-db08-4cbb-aa31-ac0454b42657' \
--header 'apiKey: 3b8f771a-8cc1-364f-be2b-9ea361f53816' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer eyJ0eXAiOiJKV1QiLCJraWQiOiJ3RjJTa1I3NWMxamZsZ1VIOWJ6Wno3Tzllemc9IiwiYWxnIjoiUlMyNTYifQ.eyJzdWIiOiJBUElJRD01MmYwNDgyNjM3OTM0ZGZmOWY5MjE1MTBhMjlhMWYwYSIsImN0cyI6Ik9BVVRIMl9TVEFURUxFU1NfR1JBTlQiLCJhdXRoX2xldmVsIjo2LCJhdWRpdFRyYWNraW5nSWQiOiJjODA1OTU2Ni1mZmIwLTQ1MGItOTA5Ny1iMTRhMjVhNWFiMWMtMjU3MDUwNjIiLCJpc3MiOiJodHRwczovL2NhYXMua2IuY3ovb3BlbmFtL29hdXRoMiIsInRva2VuTmFtZSI6ImFjY2Vzc190b2tlbiIsInRva2VuX3R5cGUiOiJCZWFyZXIiLCJhdXRoR3JhbnRJZCI6IkFRNzBZcFduekpKTmFnc1h4S3BucmoxVWd3NCIsImF1ZCI6IktpZmxpLTE2MzUiLCJuYmYiOjE2NTUzMDE3MjUsImdyYW50X3R5cGUiOiJyZWZyZXNoX3Rva2VuIiwic2NvcGUiOlsiYWRhYSJdLCJhdXRoX3RpbWUiOjE2MjM3NTczOTIsInJlYWxtIjoiLyIsImV4cCI6MTY1NTMwMTkwNSwiaWF0IjoxNjU1MzAxNzI1LCJleHBpcmVzX2luIjoxODAsImp0aSI6Ik5JRVMydVpsTk1teWNQSXNjRHVCQVAtRElHQSJ9.wEMoI5IMETzyBkJl6DMkqLCbsJgaLaKMeN1WuHvNwfZUs53aCgkWh9133PWCi36GrrySoNRWVO-lXhb-rgnwr984tXj9I6HgnoQWwvtGkPyh5sVe7pTVdomhpIue9aqAO-r0HlRRex_deDBEMwGXRhGuBmBpJNM3NI4kPCNL44OS4-120Qguhjoxv3XftYI8M8v94fqUqvj_tIew0Ms1FZzMfnzdiUStE87j8-jt5hrXMqP6w5riEagpzpUsCPmc4uedsn3uaL7GHoOe3hi1YNV7wOaQprA8xRhj751dG9xE5HCqjbB9wsjZO2Q17NOmIrnDyBKtwMlKnfEv-TLvfg' \](<curl --location --request GET 'https://api.kb.cz/open/api/adaa/v1/accounts' \
```

### Response Accounts

```json
[
  {
    "accountId": "SU1iL3NaSmR1b3NYWEZLOTk2MG8rNVV6VzB4MzAvV3ExTWpHQVRmL2JNT2N3RWVCa0VXQVA3MnNabkJTc3BteldvNWNGT1U4U1VBbDREWXY1WlZMOGc9PQ",
    "iban": "CZ3201000000863596610267",
    "currency": "CZK"
  },
  {
    "accountId": "aGZ0dCtjeTAzQjRabXN5OE9wYVZFeFA1Rk1Oa3hiQmNLMDVnTWdHRjJ2bWF6YVNZbTdhN04rWDdMYUV2aWVFbW1JZy94ckE1SlRJdys3bVpoSy93bHc9PQ",
    "iban": "CZ5401000001154933990227",
    "currency": "CZK"
  },
  {
    "accountId": "eXBCcDBLUEFCT0Y0MUFSS2x6b0RNZUJHZzJHdk5wSlhFWWdKeWEySFlabkU4OEZJQTcxU05kLzc1SnFKa0dlZmF2RzRQbHgrVDY1QXZvZHhNWXZ1Vnc9PQ",
    "iban": "CZ0301000001158830140287",
    "currency": "CZK"
  },
  {
    "accountId": "MlU5bnduTlVrY3p2S1NLd1UrWXc4QVNsbUhwaGVTcHVlaVJFbGFlWVM2OERBc2psMi9TcXQrV0dOUTZSN1oxOVFUSW80Njd6RW5MbFlPbEN5MkdmUUE9PQ",
    "iban": "CZ7901000001232334800277",
    "currency": "CZK"
  },
  {
    "accountId": "VlNyQjNMekpwMXo4WGJ4LzdQS2x3cm5iY3FIUHJ5djVIbkRWaHVkdHlRVjFWTnVTRzNUMzN2UHBjMERhaS9GbnE3aTlnSTVBUjdZWGR6MG1GeThFalE9PQ",
    "iban": "CZ2301000001071660240207",
    "currency": "CZK"
  }
]
```

---

[Continue to Balances...](./Balances)
