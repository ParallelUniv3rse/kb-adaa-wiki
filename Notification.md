# Subscribe notification

If you want to receive information about payments made on your account using this API.

## Request

```js
curl --location --request POST 'https://api.kb.cz/open/api/adaa/v1/accounts/NUZZUGh1NlpMV2ErbThHRGdCTytHN01SY1ZVVVN3RDdRN3loUGdkK2pKQk5GMFU1WTZvNnJnRWE2em1pK3NOUmdvVEtTd3JDSFJqQi9tYUsvaW9Zd2c9PQ/transactions/event-subscriptions' \
--header 'x-correlation-id: 6491e392-e4ef-46a3-bd68-6b0696ab6cf3' \
--header 'x-api-key: Bearer 3a7f779a-8cc1-364f-be2b-9ea161f63817' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer eyJ0eXAiOiJKV1QiLCJraWQiOiJ3RjJTa1I3NWMxamZsZ1VIOWJ6Wno3Tzllemc9IiwiYWxnIjoiUlMyNTYifQ.eyJzdWIiOiJBUElJRD01MmYwNDgyNjM3OTM0ZGZmOWY5MjE1MTBhMjlhMWYwYSIsImN0cyI6Ik9BVVRIMl9TVEFURUxFU1NfR1JBTlQiLCJhdXRoX2xldmVsIjo2LCJhdWRpdFRyYWNraW5nSWQiOiJhYmY1ZjE3Yi0wYjEwLTRjYjAtYWJkMi1iN2U4OGFhYTM4ZDgtNTcwMjgyNDkiLCJpc3MiOiJodHRwczovL2NhYXMua2IuY3ovb3BlbmFtL29hdXRoMiIsInRva2VuTmFtZSI6ImFjY2Vzc190b2tlbiIsInRva2VuX3R5cGUiOiJCZWFyZXIiLCJhdXRoR3JhbnRJZCI6IjF1bzJ1ZHNjS0dLSWQwVjFFT2ZzRW1sUUtQcyIsImF1ZCI6IktpZmxpLTE2MzUiLCJuYmYiOjE2NTU5NzE2NjksImdyYW50X3R5cGUiOiJyZWZyZXNoX3Rva2VuIiwic2NvcGUiOlsiYWRhYSJdLCJhdXRoX3RpbWUiOjE2NTUzNzcyNzMsInJlYWxtIjoiLyIsImV4cCI6MTY1NTk3MTg0OSwiaWF0IjoxNjU1OTcxNjY5LCJleHBpcmVzX2luIjoxODAsImp0aSI6IlhDOWdKcVJBVVBOdDVSbFZqUjVZME1UdlQyWSIsImNhYXNPcGVyYXRpb25JZCI6IjUyNzYyMTc3NmRiODQ0MTg5MGJjM2MzM2RkZjYzYmVlIn0.cLirxtAxy7bOao5sdXUBR118cHvasHoe_YMlWs51iR7Y-T4bwX6XbKWVlqeIqe62J4r17ZCsDvagScLjabGDji8zwkJvX8are9d3RouepVaza54whBtg6QS7ItE7IGiqlQCfod4Pz39Fa_0dmdI_nfrU_VST4l99jL4chFD5v0JOZ5tFBYiRcXl6Rc_msYX5DvGb40_PNPQVQgUlMm1j97qiSXfs_NTsk7o8uGw_bE6V1OlnpDDu3JjTgi2wbaOp6KPPYWIc9o2rdmUr4nMzaaU5JVEZkn4gD8Dojbcr9PhLyUaH7ACWWKguolK3WjFQj6ROI2nJ0tEF-hphnS8reA' \
--data-raw '{
  "eventApiUrl": "https://company.org/event-api/v1",
  "eventApiKey": "Q1oxMzAxMDAwOTAxMTQ3NzcxODAwMjI3OkNaSw"
}'
```

## Response

```js
{
    "subscriptionId": "6edba5aa-f3aa-431b-90e0-ed3e0ff1d3c6",
    "eventApiUrl": "https://company.org/event-api/v1",
    "eventApiVersion": "1.0",
    "status": "ACTIVE"
}
```

# Get subscription information

## Request

```js
curl --location --request GET 'https://api.kb.cz/open/api/adaa/v1/accounts/eXBCcDBLUEFCT0Y0MUFSS2x6b0RNZUJHZzJHdk5wSlhFWWdKeWEySFlabkU4OEZJQTcxU05kLzc1SnFKa0dlZmF2RzRQbHgrVDY1QXZvZHhNWXZ1Vnc9PQ/transactions/event-subscriptions/11ba81e1-412e-4699-886a-d2268a7cb3f6' \
--header 'x-correlation-id: 15218ba0-20c2-4574-b1a7-f5d63d7a31b3' \
--header 'x-api-key: Bearer 3a7f779a-8cc1-364f-be2b-9ea161f63817' \
--header 'Authorization: Bearer eyJ0eXAiOiJKV1QiLCJraWQiOiJ3RjJTa1I3NWMxamZsZ1VIOWJ6Wno3Tzllemc9IiwiYWxnIjoiUlMyNTYifQ.eyJzdWIiOiJBUElJRD01MmYwNDgyNjM3OTM0ZGZmOWY5MjE1MTBhMjlhMWYwYSIsImN0cyI6Ik9BVVRIMl9TVEFURUxFU1NfR1JBTlQiLCJhdXRoX2xldmVsIjo2LCJhdWRpdFRyYWNraW5nSWQiOiJhYmY1ZjE3Yi0wYjEwLTRjYjAtYWJkMi1iN2U4OGFhYTM4ZDgtNTcxODkwMTkiLCJpc3MiOiJodHRwczovL2NhYXMua2IuY3ovb3BlbmFtL29hdXRoMiIsInRva2VuTmFtZSI6ImFjY2Vzc190b2tlbiIsInRva2VuX3R5cGUiOiJCZWFyZXIiLCJhdXRoR3JhbnRJZCI6IjF1bzJ1ZHNjS0dLSWQwVjFFT2ZzRW1sUUtQcyIsImF1ZCI6IktpZmxpLTE2MzUiLCJuYmYiOjE2NTU5NzMwMzIsImdyYW50X3R5cGUiOiJyZWZyZXNoX3Rva2VuIiwic2NvcGUiOlsiYWRhYSJdLCJhdXRoX3RpbWUiOjE2NTUzNzcyNzMsInJlYWxtIjoiLyIsImV4cCI6MTY1NTk3MzIxMiwiaWF0IjoxNjU1OTczMDMyLCJleHBpcmVzX2luIjoxODAsImp0aSI6Imd1bG43WDc2LW9qYkQwUXUwLUZCOGtsSk11QSIsImNhYXNPcGVyYXRpb25JZCI6IjUyNzYyMTc3NmRiODQ0MTg5MGJjM2MzM2RkZjYzYmVlIn0.YzGEJfML17F2zA9TWh1pHelLmTRYDAHxLdMcF5MD-IXSNM-zHuR_S32LVTu6o68Tubo5-Erk3OkzWvr_z70MAJ8taPdNW4aj9qGluF1tgqoD9nCBaVNJDToKEkVDsv2BZmkNFDe_qwqP2cXedYhFdgoRRuydQ3mzlUytwysQJwT8j83uCf_EVLJJA7wteSEUViloOM5fbEwEvsB4LZLPG2VTpqC3dXzfhOVFw2Y4f6o7G3RiGSBmYtt9_3WBb47vh0EM6jV3TjG5XUFfOXPGcV1_F6LqytsnGKa2QzmCcrnKkMhCH-grhZcy3XJ7AncaC2bKuLPJnP83ZfyazRVeQg'
```

## Response

```js
{
    "subscriptionId": "6edba5aa-f3aa-431b-90e0-ed3e0ff1d3c6",
    "eventApiUrl": "https://notification-subscriber.herokuapp.com/adaa-notification-subscriber",
    "eventApiVersion": "1.0",
    "status": "ACTIVE"
}

```

# Unsubscribe notification

## Request

```js
curl --location --request DELETE 'https://api.kb.cz/open/api/adaa/v1/accounts/eXBCcDBLUEFCT0Y0MUFSS2x6b0RNZUJHZzJHdk5wSlhFWWdKeWEySFlabkU4OEZJQTcxU05kLzc1SnFKa0dlZmF2RzRQbHgrVDY1QXZvZHhNWXZ1Vnc9PQ/transactions/event-subscriptions/622f2380-abd7-43aa-9a20-1a32a80b726d' \
--header 'x-correlation-id: 7640f544-7121-4805-96c6-a4879593cdc7' \
--header 'x-api-key: Bearer 3a7f779a-8cc1-364f-be2b-9ea161f63817' \
--header 'Authorization: Bearer eyJ0eXAiOiJKV1QiLCJraWQiOiJ3RjJTa1I3NWMxamZsZ1VIOWJ6Wno3Tzllemc9IiwiYWxnIjoiUlMyNTYifQ.eyJzdWIiOiJBUElJRD01MmYwNDgyNjM3OTM0ZGZmOWY5MjE1MTBhMjlhMWYwYSIsImN0cyI6Ik9BVVRIMl9TVEFURUxFU1NfR1JBTlQiLCJhdXRoX2xldmVsIjo2LCJhdWRpdFRyYWNraW5nSWQiOiIxYTAwMDU3ZS02YzJjLTRmZmYtODRlZS04ZDU1MzE5OTgzYTAtNTgxNDczNTYiLCJpc3MiOiJodHRwczovL2NhYXMua2IuY3ovb3BlbmFtL29hdXRoMiIsInRva2VuTmFtZSI6ImFjY2Vzc190b2tlbiIsInRva2VuX3R5cGUiOiJCZWFyZXIiLCJhdXRoR3JhbnRJZCI6IjF1bzJ1ZHNjS0dLSWQwVjFFT2ZzRW1sUUtQcyIsImF1ZCI6IktpZmxpLTE2MzUiLCJuYmYiOjE2NTU5NzMzNzAsImdyYW50X3R5cGUiOiJyZWZyZXNoX3Rva2VuIiwic2NvcGUiOlsiYWRhYSJdLCJhdXRoX3RpbWUiOjE2NTUzNzcyNzMsInJlYWxtIjoiLyIsImV4cCI6MTY1NTk3MzU1MCwiaWF0IjoxNjU1OTczMzcwLCJleHBpcmVzX2luIjoxODAsImp0aSI6IjR6dmhxQzRheWVkakw0WWxCc05aUm90MF9hRSIsImNhYXNPcGVyYXRpb25JZCI6IjUyNzYyMTc3NmRiODQ0MTg5MGJjM2MzM2RkZjYzYmVlIn0.nG4gliOMVWbadIAWChglg2yQcqNocgF5-z0ehNIE4Y--C63Wr4sonLpCPJPwvlm1Tb3z10HxN1TUwmvDUHvZwKiomAaa9MRzmr4-oJwc8cr_K1b3dB6FeN6r01WH6RHTLK0I-WAEONZR7kmaZP4jNPB_jVNR4Lx_6vVqNsoo2PApXzMx1DAFZQsNy5JIryGuN2GA6B9LF3XqpN6o-BpKnNn9Dsj8T0QiVK716ChSU1BM3l7MpCulfzRhEzhJB3as5GKE0z8RguBibKMw88oU8WT3jBeaHEQnRaGaKc0MrMnSoT2BlG42vekXqDEhu-42Of_Y7VKgsFbk8HolOztwHQ'
```

## Response

HTTP 204

# Your API to receive notification

- [specification](https://github.com/komercka/adaa-eventapi-spring-boot-example/blob/master/rest/src/main/resources/openapi/adaa-event-api.yaml)
- if you want to limit network traffic, incoming requests from the bank come from IP addresses:
  - 194.50.202.179
  - 194.50.226.179
