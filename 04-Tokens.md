# Tokens

[//]: # (TODO: add links to the Sandbox and Production API docs)

- Obtain the Authorization code
- Exchange Authorization code for Refresh token and Access token
- Keep getting Access tokens from the Refresh token

## Authorization code

> **Authorization code validity** \
> Code is valid for only 2 minutes

- Construct the URL and redirect your user (_Client of KB_) to the URL.

### Authorization code Request

You need the `client_id` from the [Application Registration](./03-Application-Registration-OAuth2.md)

**Sandbox** `https://api-gateway.kb.cz/sandbox/oauth2-authorization-ui/v2/` \
**Production** `https://login.kb.cz/autfe/ssologin`

#### URL parameters
- `response_type` - "code"
- `client_id` - client_id from previous step
- `redirect_uri` - your URL to redirect to after success
- `scope` - scopes you want to request (see [Scopes](./03-Application-Registration-OAuth2#scope))

Constructed URL example:
```
GET
https://login.kb.cz/autfe/ssologin?response_type=code&client_id=Nejlepsiprodukt-4176&redirect_uri=https://client.example.org/callback&scope=adaa%20card_data
```

### Authorization code Response

- Get the `code` from the URL parameter in the callback URL.

```
302 Found
https://client.example.org/callback?code=-_N2RrJRCMgd__JGqUlB_KaFNpo&iss=https%3A%2F%2Fcaas.kb.cz%2Fopenam%2Foauth2&client_id=Nejlepsiprodukt-4176
```

## Refresh token

> **Token validity** \
> refresh_token validity is  12 months

**How to prolong refresh_token?** \
Read the FAQ [How do I prolong the tokens?](./FAQ.md#how-do-i-prolong-the-tokens)

### Refresh token Request

```bash
curl --location --request POST 'https://api-gateway.kb.cz/oauth2/v2/access_token' \
--header 'x-correlation-id: 9f1670dd-db08-4cbb-aa31-ac0454b42657' \
--header 'apiKey: 3a7f779a-8cc1-364f-be2b-9ea161f63817' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode 'redirect_uri=https://app.kifli.cz/callback' \
--data-urlencode 'code=6W6hsrmHBqN8J6nEW3iPfbB97X8' \
--data-urlencode 'client_id=Kifli-1635' \
--data-urlencode 'client_secret=Xe-_BCRf9mi7uyEzIQiLGA' \
--data-urlencode 'grant_type=authorization_code'
```

### Refresh token Response

```json
{
  "access_token": "eyJ0eXAiOiJKV1QiLCJraWQiOiJJTDdyR3BrMXNzNE9id0VIYmIrQ1RBbEozbzQ9IiwiYWxnIjoiUlMyNTYifQ.eyJzdWIiOiJBUElJRD0wZTYyNjQxMmJhYzg0Mzc4ODk0ZDFmNjM3MzQ4N2U4NiIsImN0cyI6Ik9BVVRIMl9TVEFURUxFU1NfR1JBTlQiLCJhdXRoX2xldmVsIjo0LCJhdWRpdFRyYWNraW5nSWQiOiIxY2YwY2I4Ni0xNDZmLTRhOTMtOWEzYS00YTQ3MmVkZDJiZmEtMTI3NTA1IiwiaXNzIjoiaHR0cHM6Ly91YXQyLWNhYXMua2IuY3ovb3BlbmFtL29hdXRoMiIsInRva2VuTmFtZSI6ImFjY2Vzc190b2tlbiIsInRva2VuX3R5cGUiOiJCZWFyZXIiLCJhdXRoR3JhbnRJZCI6IjFFd3VhZ1F0bDlvcV95eUg3OG1LWkYxdmxMOCIsImF1ZCI6IkFBQUF1dHB1dDMzQUItNDcwMSIsIm5iZiI6MTYzMTg2Nzg2NSwiZ3JhbnRfdHlwZSI6ImF1dGhvcml6YXRpb25fY29kZSIsInNjb3BlIjpbImNhcmRfZGF0YSIsImFkYWEiXSwiYXV0aF90aW1lIjoxNjMxODY3ODExLCJyZWFsbSI6Ii8iLCJleHAiOjE2Mzk2NDM4NjUsImlhdCI6MTYzMTg2Nzg2NSwiZXhwaXJlc19pbiI6Nzc3NjAwMCwianRpIjoiaklwQzJaQnZHOFdCRENMajd1elRYU2Y1UnRnIiwiY2Fhc09wZXJhdGlvbklkIjoiNDA1Y2Q0YWZiNzdmNDM1MTliNjljMmI1MTBhMmUxNWEifQ.McYFKolLFP4P2mybvgdtp3j5nv0dkZD_dRNKlBGDSSuYSifCvuYmt-F6ry1tkG3KsXNOqn1Jnb5hS6qwQpMMZr0lZOgUrbbPXUE-H2LB0-9C0Cv10kFK93faZmi__a3GRcC3KYYcYVykNmcGWTz7VBpt_yVme2Z7Piy5X718WNqPn2wd9dLhyW644Jpv0UA61GH361m80iJIOXjJPa0hY-xyOQ9-9ir1i8LObCI--YiQtGUOIa2t2K8qD8K4LBQCxy3Y-QW7ByDFBCP1n2a1wM_Vs3dZ6u9FsW0t-amOQTXiGBk_86zlR0Tgmn8zoYzv5KsL2qlzLVzWrx89eIySBg",
  "refresh_token": "eyJ0eXAiOiJKV1QiLCJraWQiOiJJTDdyR3BrMXNzNE9id0VIYmIrQ1RBbEozbzQ9IiwiYWxnIjoiUlMyNTYifQ.eyJzdWIiOiJBUElJRD0wZTYyNjQxMmJhYzg0Mzc4ODk0ZDFmNjM3MzQ4N2U4NiIsImN0cyI6Ik9BVVRIMl9TVEFURUxFU1NfR1JBTlQiLCJhdXRoX2xldmVsIjo0LCJhdWRpdFRyYWNraW5nSWQiOiIxY2YwY2I4Ni0xNDZmLTRhOTMtOWEzYS00YTQ3MmVkZDJiZmEtMTI3NTA0IiwiaXNzIjoiaHR0cHM6Ly91YXQyLWNhYXMua2IuY3ovb3BlbmFtL29hdXRoMiIsInRva2VuTmFtZSI6InJlZnJlc2hfdG9rZW4iLCJhdXRoTW9kdWxlcyI6IkNhYXNQYXNzd29yZHxPcGVyYXRpb25TdGF0ZUNoZWNrZXJ8UGlja2VyfE90cHxSZXF1ZXN0QmluZGVyfENhYXNBZGFwdGl2ZSIsInRva2VuX3R5cGUiOiJCZWFyZXIiLCJhdXRoR3JhbnRJZCI6IjFFd3VhZ1F0bDlvcV95eUg3OG1LWkYxdmxMOCIsImF1ZCI6IkFBQUF1dHB1dDMzQUItNDcwMSIsImFjciI6IjAiLCJuYmYiOjE2MzE4Njc4NjUsImdyYW50X3R5cGUiOiJhdXRob3JpemF0aW9uX2NvZGUiLCJzY29wZSI6WyJjYXJkX2RhdGEiLCJhZGFhIl0sImF1dGhfdGltZSI6MTYzMTg2NzgxMSwicmVhbG0iOiIvIiwiZXhwIjoxNjYzNDI0NzkxLCJpYXQiOjE2MzE4Njc4NjUsImV4cGlyZXNfaW4iOjMxNTU2OTI2LCJqdGkiOiI2a2NCNVBnLVJNTUlyN3YwLUhpRGFTaUltZWcifQ.ufH9vFCRGtJuctWdNDxcHaEbxbdAP_2vukeAzGNIofF-CATqp2gkBmwpOs0Fp75opYrslImoevGiUJ5DlbFiheyhL9N1rSTEPy2TmRgl8bd4_liJQVpp-yevH9eTyqsQkELkyCS-e0KGWeTcPfXe7PGQMwkneuiHGDLxNxyxVPg1qMXdApDdmLbIzoIxHDOIRA6eCR6uAwwOjgz3piJs8qLiBgykuTweE-zR1gSjQV-rPJknuf-GsntwwVCa3IwFA89tT9X_oh2bJQGhinFyHFvLclEWTCNU0ArFBkcZ6m9ez24r2WwflsBQFQw-lPfQ0DNuck33Op0c5VLbvQk8xw"
}
```

## Access token

> **Token validity** 
> - access_token validity is 3 minutes
> - access token is intended to be reused until the time of its expiration
> - excessive requests to obtain a new access token may result in a status response `429 Too Many Requests`

### Access token Request

```bash
curl --location --request POST 'https://api-gateway.kb.cz/oauth2/v2/access_token' \
--header 'x-correlation-id: 9f1670dd-db08-4cbb-aa31-ac0454b42657' \
--header 'apiKey: 3a7f779a-8cc1-364f-be2b-9ea161f63817' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode 'redirect_uri=https://app.kifli.cz/callback' \
--data-urlencode 'client_id=Kifli-1635' \
--data-urlencode 'client_secret=Xe-_BCRf9mi7uyEzIQiLGA' \
--data-urlencode 'refresh_token=eyJ0eXAiOiJKV1QiLCJraWQiOiJ3RjJTa1I3NWMxamZsZ1VIOWJ6Wno3Tzllemc9IiwiYWxnIjoiUlMyNTYifQ.eyJzdWIiOiJBUElJRD01MmYwNDgyNjM3OTM0ZGZmOWY5MjE1MTBhMjlhMWYwYSIsImN0cyI6Ik9BVVRIMl9TVEFURUxFU1NfR1JBTlQiLCJhdXRoX2xldmVsIjo2LCJhdWRpdFRyYWNraW5nSWQiOiJlYzU5NDNjZi00ZGE4LTQ3ZDQtYjJmOS05ODNkMmQyYzE4MjEtMTU1ODg3MTgiLCJpc3MiOiJodHRwczovL2NhYXMua2IuY3o6NDQzL29wZW5hbS9vYXV0aDIiLCJ0b2tlbk5hbWUiOiJyZWZyZXNoX3Rva2VuIiwiYXV0aE1vZHVsZXMiOiJQYWFUfFBpY2tlcnxSZXF1ZXN0QmluZGVyfENhYXNBZGFwdGl2ZSIsInRva2VuX3R5cGUiOiJCZWFyZXIiLCJhdXRoR3JhbnRJZCI6IkFRNzBZcFduekpKTmFnc1h4S3BucmoxVWd3NCIsImF1ZCI6IktpZmxpLTE2MzUiLCJhY3IiOiIwIiwibmJmIjoxNjIzNzU3NDM0LCJncmFudF90eXBlIjoiYXV0aG9yaXphdGlvbl9jb2RlIiwic2NvcGUiOlsiYWRhYSJdLCJhdXRoX3RpbWUiOjE2MjM3NTczOTIsInJlYWxtIjoiLyIsImV4cCI6MTY1NTMxNDM2MCwiaWF0IjoxNjIzNzU3NDM0LCJleHBpcmVzX2luIjozMTU1NjkyNiwianRpIjoiNVhtYW4zbzNIb2lnaFlZZjJWS3RjRmNwUzZBIn0.0PbCum-UPt3E2Bq0xpvGB4LX29fLntiqeJP-lxpSSHt0fSEv_PmSkME19mpRaEod_grkWLtmnapphd2g2olQ_VeiRqYY_0v67De-D43E_tPm8Ei1dV_VBrqR0TJLtzLGRm8Gd7FtvSwNzc8Us3HyHlxU4yJfqCFTeln5xZzowgJ1kOLpUsG7BIClRyHvQwUAncPYF2Rx90_2IkW3Q18IIROSoA8CUajq18Yw8ulfFsMQ0xM_XB5aiUXnENUQYssSZTRL3xk5CTnm9F0I_p-u0Fa51l_Z-TU7CN5maKxJYETjFgMEa_dewSQ2x7AQoqC2LSrLggN0oHHlNyEJ_wP8rQ' \
--data-urlencode 'grant_type=refresh_token'
```

### Access token Response

```json
{
  "access_token": "eyJ0eXAiOiJKV1QiLCJraWQiOiJ3RjJTa1I3NWMxamZsZ1VIOWJ6Wno3Tzllemc9IiwiYWxnIjoiUlMyNTYifQ.eyJzdWIiOiJBUElJRD01MmYwNDgyNjM3OTM0ZGZmOWY5MjE1MTBhMjlhMWYwYSIsImN0cyI6Ik9BVVRIMl9TVEFURUxFU1NfR1JBTlQiLCJhdXRoX2xldmVsIjo2LCJhdWRpdFRyYWNraW5nSWQiOiJmZjhkZTdlNy0xMGMxLTRiNzctYmY3Yy0xY2ZkMzYzMDI5MjItMzAyMzg4NzEiLCJpc3MiOiJodHRwczovL2NhYXMua2IuY3ovb3BlbmFtL29hdXRoMiIsInRva2VuTmFtZSI6ImFjY2Vzc190b2tlbiIsInRva2VuX3R5cGUiOiJCZWFyZXIiLCJhdXRoR3JhbnRJZCI6IjF1bzJ1ZHNjS0dLSWQwVjFFT2ZzRW1sUUtQcyIsImF1ZCI6IktpZmxpLTE2MzUiLCJuYmYiOjE2NTUzNzczNTUsImdyYW50X3R5cGUiOiJyZWZyZXNoX3Rva2VuIiwic2NvcGUiOlsiYWRhYSJdLCJhdXRoX3RpbWUiOjE2NTUzNzcyNzMsInJlYWxtIjoiLyIsImV4cCI6MTY1NTM3NzUzNSwiaWF0IjoxNjU1Mzc3MzU1LCJleHBpcmVzX2luIjoxODAsImp0aSI6IjVqN0d3U1ZWcXlzU0NoX1hoQmxMaUxTTV9MRSIsImNhYXNPcGVyYXRpb25JZCI6IjUyNzYyMTc3NmRiODQ0MTg5MGJjM2MzM2RkZjYzYmVlIn0.Dy_60fOTOclbNVR4gUybTV8XDdcyXxqZoQGoRZq5Ou0PDgJiDcYxKIUMvNQqtW06kEVgCCCvTzrwiVH8ArteCWGMBQnjANwgSm8LB8567tzKN4NxAar3TXSd55ZrDhbk1SbzJyaDnj9qMsIMf9a1u4H6JMeyAGA1MK6XehsJ70dZzN_R6YaB3hG5iMxUG_-z-_cTWs29rPAoFbRUGKuSzaXRyefmiS-pJXgshfoey4YF6swyI3K-MalkzgW1WzGxn7vRwjeQ5VyxNsDsygsjJ90qgcHNqvdglCyWAasMxxqE6CgfVv4J7Ym0fnu9HK0QyPNaUlQNwZ0QeXfSPBSFrg",
  "scope": "adaa",
  "token_type": "Bearer",
  "expires_in": 179
}
```

---

## Next step
[Continue to Accounts...](./05-Accounts)