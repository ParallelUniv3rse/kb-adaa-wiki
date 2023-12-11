# How does it work?

![Process flow](./img/flow.min.png)

## Developer registers on [API portal](https://developers.kb.cz)

- create application
- subcribe to API (Client Registration sandbox, OAuth2 sandbox, Adaa sandbox API)
- create API key (apiKey)

# Software Statements

> **JWT tokens validity**
>
> - The JWT statement is valid for 12 months
> - Please fill in email, we will contact you about news or tokens validity

## Request

> **Prerequisites for this request**
>
> Qualified certificate from
>
> - I.CA
> - PostSignum

```js
curl --location 'https://api-gateway.kb.cz/sandbox/client-registration/v2/software-statements' \
--header 'x-correlation-id: c41ca7c4-5935-4e65-9729-8ce0985225b4' \
--header 'apiKey: eyJ4NXQiOiJPVFl5T0RCa1l6YzNNemhpWkdVd05XWmpNemhqWlRsbU1EaGhPRFU0WVRJMk5qUTFPVE5sTkE9PSIsImtpZCI6InByb2RfYXBpbSIsInR5cCI6IkpXVCIsImFsZyI6IlJTMjU2In0=.eyJzdWIiOiJLQi1DVVNcL21pbG9zQHNvbnRhay5ldUBjYXJib24uc3VwZXIiLCJhcHBsaWNhdGlvbiI6eyJvd25lciI6IktCLUNVU1wvbWlsb3NAc29udGFrLmV1IiwidGllclF1b3RhVHlwZSI6bnVsbCwidGllciI6IlVubGltaXRlZCIsIm5hbWUiOiJDbGllbnQtUmVnaXN0cmF0aW9uLVNhbmRib3hfdjJfMSIsImlkIjozMywidXVpZCI6IjhmZDY4MmI4LWM3MmYtNGMwMS1iNmRlLWZmMjU1MjhlZDMxMSJ9LCJpc3MiOiJodHRwczpcL1wvYXBpbS5wcm9kLm9iLW91dGJvdW5kLmtiY2xvdWRcL29hdXRoMlwvdG9rZW4iLCJ0aWVySW5mbyI6eyJVbmxpbWl0ZWQiOnsidGllclF1b3RhVHlwZSI6InJlcXVlc3RDb3VudCIsImdyYXBoUUxNYXhDb21wbGV4aXR5IjowLCJncmFwaFFMTWF4RGVwdGgiOjAsInN0b3BPblF1b3RhUmVhY2giOnRydWUsInNwaWtlQXJyZXN0TGltaXQiOjAsInNwaWtlQXJyZXN0VW5pdCI6bnVsbH19LCJrZXl0eXBlIjoiUFJPRFVDVElPTiIsInN1YnNjcmliZWRBUElzIjpbeyJzdWJzY3JpYmVyVGVuYW50RG9tYWluIjoiY2FyYm9uLnN1cGVyIiwibmFtZSI6IkNsaWVudC1SZWdpc3RyYXRpb24tU2FuZGJveCIsImNvbnRleHQiOiJcL3NhbmRib3hcL2NsaWVudC1yZWdpc3RyYXRpb25cL3YyIiwicHVibGlzaGVyIjoiYWRtaW4iLCJ2ZXJzaW9uIjoidjIiLCJzdWJzY3JpcHRpb25UaWVyIjoiVW5saW1pdGVkIn1dLCJpYXQiOjE3MDIwNDEzNDcsImp0aSI6IjNjNDZkNGJiLTEyZWMtNDI2Ni04MmQxLWNlZjZjMzUzM2M2MyJ9.QXaJy0rqw9S2XLRtDEpQExoSs3IE_0pJWvZ_5en4EdYiKnK5p2wSL6z51xzAuVVGvqUivF_akRF3NHnMMy44pURty5dnWDl8rCaIvGzyWHqawnNunD8bqHzYzEi6ilh399v_Xi4XEIZvj6GL8thSXpNa4cEMAagtxVHb_ljqLV5EwIirbEGbeRQlWPO6dfSZ83qyF_XrADMzEv5dnZu9wJ0uJrQ0ooXQaArjLxz2RyRQkbKLy-fAXZ0aFAdGomV9Kdzsq3UZd5Ll74rJM0DBUq1YONr7JVc_IxOuG3IbrydA0lbA9CQxCCrl9ZT-b8YteUSVaQObhzlnCPI5FwZXLw==' \
--header 'Content-Type: application/json' \
--data-raw '{
  "softwareName": "Nejlepší produkt",
  "softwareNameEn": "Best product",
  "softwareId": "f64bf2e447e545228c78e07b081a82ee",
  "softwareVersion": "1.0",
  "softwareUri": "https://client.example.org",
  "redirectUris": [
    "https://client.example.org/callback",
    "https://client.example.org/callback-backup"
  ],
  "tokenEndpointAuthMethod": "client_secret_post",
  "grantTypes": [
    "authorization_code"
  ],
  "responseTypes": [
    "code"
  ],
  "registrationBackUri": "https://client.example.org/backuri",
  "contacts": [
    "email: example@goodsoft.com"
  ],
  "logoUri": "https://client.example.org/logo.png",
  "tosUri": "https://client.example.org/tos",
  "policyUri": "https://client.example.org/policy"
}'
```

## Response

> **Inspect the content of the JWT body (you can do it by using [jwt.io](https://jwt.io))**

HTTP 201

>

```text
eyJhbGciOiJIUzI1NiJ9.eyJ2ZW5kb3JOYW1lIjoiQ29tcGFueSBhLnMuIiwic29mdHdhcmVOYW1lIjoiTmVqbGVwxaHDrSBwcm9kdWt0Iiwic29mdHdhcmVOYW1lRW4iOiJCZXN0IHByb2R1Y3QiLCJzb2Z0d2FyZUlkIjoiZjY0YmYyZTQ0N2U1NDUyMjhjNzhlMDdiMDgxYTgyZWUiLCJzb2Z0d2FyZVZlcnNpb24iOiIxLjAiLCJzb2Z0d2FyZVVyaSI6Imh0dHBzOi8vY2xpZW50LmV4YW1wbGUub3JnIiwicmVkaXJlY3RVcmlzIjpbImh0dHBzOi8vY2xpZW50LmV4YW1wbGUub3JnL2NhbGxiYWNrIiwiaHR0cHM6Ly9jbGllbnQuZXhhbXBsZS5vcmcvY2FsbGJhY2stYmFja3VwIl0sInRva2VuRW5kcG9pbnRBdXRoTWV0aG9kIjoiY2xpZW50X3NlY3JldF9wb3N0IiwiZ3JhbnRUeXBlcyI6WyJhdXRob3JpemF0aW9uX2NvZGUiXSwicmVzcG9uc2VUeXBlcyI6WyJjb2RlIl0sInJlZ2lzdHJhdGlvbkJhY2tVcmkiOiJodHRwczovL2NsaWVudC5leGFtcGxlLm9yZy9iYWNrdXJpIiwiY29udGFjdHMiOlsiZW1haWw6IGV4YW1wbGVAZ29vZHNvZnQuY29tIl0sImxvZ29VcmkiOiJodHRwczovL2NsaWVudC5leGFtcGxlLm9yZy9sb2dvLnBuZyIsInRvc1VyaSI6Imh0dHBzOi8vY2xpZW50LmV4YW1wbGUub3JnL3RvcyIsInBvbGljeVVyaSI6Imh0dHBzOi8vY2xpZW50LmV4YW1wbGUub3JnL3BvbGljeSJ9.Fw11ePNty7aimkm3yBYMoK5L-8Blpec4CafNJ-giC4g
```

# Application Registration - OAuth2

```json
{
  "clientName": "Nejlepší produkt",
  "clientNameEn": "Best product",
  "applicationType": "web",
  "redirectUris": ["http://localhost:8888/transactions"],
  "scope": ["adaa"],
  "softwareStatement": "eyJhbGciOiJIUzI1NiJ9.eyJ2ZW5kb3JOYW1lIjoiQ29tcGFueSBhLnMuIiwic29mdHdhcmVOYW1lIjoiTmVqbGVwxaHDrSBwcm9kdWt0Iiwic29mdHdhcmVOYW1lRW4iOiJCZXN0IHByb2R1Y3QiLCJzb2Z0d2FyZUlkIjoiZjY0YmYyZTQ0N2U1NDUyMjhjNzhlMDdiMDgxYTgyZWUiLCJzb2Z0d2FyZVZlcnNpb24iOiIxLjAiLCJzb2Z0d2FyZVVyaSI6Imh0dHBzOi8vY2xpZW50LmV4YW1wbGUub3JnIiwicmVkaXJlY3RVcmlzIjpbImh0dHBzOi8vY2xpZW50LmV4YW1wbGUub3JnL2NhbGxiYWNrIiwiaHR0cHM6Ly9jbGllbnQuZXhhbXBsZS5vcmcvY2FsbGJhY2stYmFja3VwIl0sInRva2VuRW5kcG9pbnRBdXRoTWV0aG9kIjoiY2xpZW50X3NlY3JldF9wb3N0IiwiZ3JhbnRUeXBlcyI6WyJhdXRob3JpemF0aW9uX2NvZGUiXSwicmVzcG9uc2VUeXBlcyI6WyJjb2RlIl0sInJlZ2lzdHJhdGlvbkJhY2tVcmkiOiJodHRwczovL2NsaWVudC5leGFtcGxlLm9yZy9iYWNrdXJpIiwiY29udGFjdHMiOlsiZW1haWw6IGV4YW1wbGVAZ29vZHNvZnQuY29tIl0sImxvZ29VcmkiOiJodHRwczovL2NsaWVudC5leGFtcGxlLm9yZy9sb2dvLnBuZyIsInRvc1VyaSI6Imh0dHBzOi8vY2xpZW50LmV4YW1wbGUub3JnL3RvcyIsInBvbGljeVVyaSI6Imh0dHBzOi8vY2xpZW50LmV4YW1wbGUub3JnL3BvbGljeSJ9.Fw11ePNty7aimkm3yBYMoK5L-8Blpec4CafNJ-giC4g",
  "encryptionAlg": "AES-256",
  "encryptionKey": "MnM1djh5L0I/RShIK01iUWVUaFdtWnEzdDZ3OXokQyY="
}
```

## Attributes

### Scopes

- adaa - account direct access api
- bpisp - batch payments
- card_data - informationb about card

### Statements

- Statement from previous step - [software statement](./Software-Statements)

## Convert to BASE64

```
ewoKICAiY2xpZW50TmFtZSI6ICJOZWpsZXDFocOtIHByb2R1a3QiLAogICJjbGllbnROYW1lRW4iOiAiQmVzdCBwcm9kdWN0IiwKICJhcHBsaWNhdGlvblR5cGUiOiAid2ViIiwKICAicmVkaXJlY3RVcmlzIjogWwogICAgImh0dHA6Ly9sb2NhbGhvc3Q6ODg4OC90cmFuc2FjdGlvbnMiCiAgXSwKICAic2NvcGUiOiBbCiAgICAiYWRhYSIKICBdLAogICJzb2Z0d2FyZVN0YXRlbWVudCI6ICJleUpoYkdjaU9pSlNVekkxTmlKOS5leUpwYzNNaU9pSkxiMjFsY3NTTmJzT3RJRUpoYm10aElITXVjaTV2TGlJc0ltbGhkQ0k2TVRVNE1EZ3lORGd4TUN3aVpYaHdJam94TlRrMk5UUTVOakV3TENKMlpXNWtiM0pPWVcxbElqb2lRbXh2YXpNM0lITXVjaTV2TGlJc0luTnZablIzWVhKbFRtRnRaU0k2SWs1bGFteGxjTVdodzYwZ2NISnZaSFZyZENJc0luTnZablIzWVhKbFRtRnRaVVZ1SWpvaVFtVnpkQ0J3Y205a2RXTjBJaXdpYzI5bWRIZGhjbVZKWkNJNklqSTFZbVkwTVRGbExXWmxaR0V0TkdFME9TMWhZVGxtTFdSbU5qZ3pORGd3TWpZMk5DSXNJbk52Wm5SM1lYSmxWbVZ5YzJsdmJpSTZJakV1TUNJc0luTnZablIzWVhKbFZYSnBJam9pYUhSMGNEb3ZMM2QzZHk1emIyWjBMWGRoY21VdVkzb2lMQ0p5WldScGNtVmpkRlZ5YVhNaU9sc2lhSFIwY0RvdkwyeHZZMkZzYUc5emREbzRPRGc0TDNSeVlXNXpZV04wYVc5dWN5SmRMQ0owYjJ0bGJrVnVaSEJ2YVc1MFFYVjBhRTFsZEdodlpDSTZJbU5zYVdWdWRGOXpaV055WlhSZmNHOXpkQ0lzSW1keVlXNTBWSGx3WlhNaU9sc2lZWFYwYUc5eWFYcGhkR2x2Ymw5amIyUmxJbDBzSW5KbGMzQnZibk5sVkhsd1pYTWlPbHNpWTI5a1pTSmRMQ0p5WldkcGMzUnlZWFJwYjI1Q1lXTnJWWEpwSWpvaWFIUjBjRG92TDNkM2R5NXpiM1JtTFhkaGNtVXVZM292Y21WbmFYTjBaWElpTENKamIyNTBZV04wY3lJNld5SmxiV0ZwYkRvZ2RHVnpkRUIwWlhOMExtOXlaeUpkTENKc2IyZHZWWEpwSWpvaWFIUjBjRG92TDNkM2R5NXpiM1JtTFhkaGNtVXVZM292Ykc5bmJ5NXdibWNpTENKMGIzTlZjbWtpT2lKb2RIUndPaTh2ZDNkM0xuTnZkR1l0ZDJGeVpTNWplaTkwYjNNaUxDSndiMnhwWTNsVmNta2lPaUpvZEhSd09pOHZkM2QzTG5OdmRHWXRkMkZ5WlM1amVpOXdiMnhwWTNraWZRLkVNejMxeUNEYWlUTkpUSTZ4UVk5ZDRzSGk4YU52aXVMRFh0TWRRc2wxLWRQajNpNTlVUjVkNThXOFl1V1VWUGZsSTc5T3JYQnFGTkVscUNlNk1xUEI5STBWODloVXJWbk9FdHNxM1hFdlB6SWFlZHBWVFE4Sk9uZWRtclFpMkRFWUlYc2RvLXd1VWk5WVdSS3ItMXlmZUlPdjBOVGFfQ0tqSHVzUzVESDlyYjlHb01Rcm84ekVLZmFlTUJSS2gyeDFqNmtJQUxobjhfOVhwcWtBb1RuQnQ5RUoyZWswckt1ZjRtQlhIYUx5bEJVRGN0cWRDdUdPZ19RUEktb1BsbFI2Q0t0R2tmb0FoZ0JyWFEzendhWGRXd0JjMjRsUTYzUkFSUmN2UGlidFNsYUZxZlNuUThiU0pfMF9mVzNnaXRsTEl5eVJqOE1QcmJaZWFkc0Fjbkt6QSIsCiAgImVuY3J5cHRpb25BbGciOiAiQUVTLTI1NiIsCiAgImVuY3J5cHRpb25LZXkiOiAiUmkxS1lVNWtVbWRWYTFod01uTTFkamg1TDBJL1JTaElLMHRpVUdWVGFGWT0iCn0=
```

## Request

ℹ️ This request put in your browser and fill value "client1"

```js
https://api-gateway.kb.cz/sandbox/client-registration-ui/v1/saml/register?registrationRequest=ewogICAgImNsaWVudE5hbWUiOiAiRXhhbXBsZUNsaWVudCIsCiAgICAiY2xpZW50TmFtZUVuIjogIkV4YW1wbGVDbGllbnQiLAogICAgImFwcGxpY2F0aW9uVHlwZSI6ICJ3ZWIiLAogICAgInJlZGlyZWN0VXJpcyI6IFsiaHR0cHM6Ly9jbGllbnQuZXhhbXBsZS5vcmcvY2FsbGJhY2siXSwKICAgICJzY29wZSI6IFsiYWRhYSJdLAogICAgImVuY3J5cHRpb25BbGciOiAiQUVTLTI1NiIsCiAgICAiZW5jcnlwdGlvbktleSI6ICJNbk0xZGpoNUwwSS9SU2hJSzAxaVVXVlVhRmR0V25FemREWjNPWG9rUXlZPSIsCiAgICAic29mdHdhcmVTdGF0ZW1lbnQiOiAiZXlKaGJHY2lPaUpTVXpJMU5pSjkuZXlKcGMzTWlPaUpMYjIxbGNzU05ic090SUVKaGJtdGhJRlJGVTFRaUxDSnBZWFFpT2pFMk5EazBNRFk0TmpFc0ltVjRjQ0k2TVRZMk5URXpNVFkyTVN3aWRtVnVaRzl5VG1GdFpTSTZJa1Y0WVcxd2JHVlBjbWRoYm1sNllYUnBiMjRpTENKMlpXNWtiM0pTWldkcGMzUnlZWFJwYjI1T2RXMWlaWElpT2lJeE1qTTBOVFlpTENKemIyWjBkMkZ5WlU1aGJXVWlPaUpGZUdGdGNHeGxRMnhwWlc1MElpd2ljMjltZEhkaGNtVk9ZVzFsUlc0aU9pSkZlR0Z0Y0d4bFEyeHBaVzUwSWl3aWMyOW1kSGRoY21WSlpDSTZJbUk0TlRkbU1UYzFORFpoTURRek9EaGlNbUprTW1Zd01EbGlOVEEwT1RobElpd2ljMjltZEhkaGNtVldaWEp6YVc5dUlqb2lNUzR3SWl3aWMyOW1kSGRoY21WVmNta2lPaUpvZEhSd2N6b3ZMMk5zYVdWdWRDNWxlR0Z0Y0d4bExtOXlaeUlzSW5KbFpHbHlaV04wVlhKcGN5STZXeUpvZEhSd2N6b3ZMMk5zYVdWdWRDNWxlR0Z0Y0d4bExtOXlaeTlqWVd4c1ltRmpheUlzSW1oMGRIQnpPaTh2WTJ4cFpXNTBMbVY0WVcxd2JHVXViM0puTDJOaGJHeGlZV05yTFdKaFkydDFjQ0pkTENKMGIydGxia1Z1WkhCdmFXNTBRWFYwYUUxbGRHaHZaQ0k2SW1Oc2FXVnVkRjl6WldOeVpYUmZZbUZ6YVdNaUxDSm5jbUZ1ZEZSNWNHVnpJanBiSW1GMWRHaHZjbWw2WVhScGIyNWZZMjlrWlNJc0luSmxabkpsYzJoZmRHOXJaVzRpWFN3aWNtVnpjRzl1YzJWVWVYQmxjeUk2V3lKamIyUmxJbDBzSW5KbFoybHpkSEpoZEdsdmJrSmhZMnRWY21raU9pSm9kSFJ3Y3pvdkwyTnNhV1Z1ZEM1bGVHRnRjR3hsTG05eVp5OWlZV05yZFhKcElpd2lZMjl1ZEdGamRITWlPbHNpWlcxaGFXdzZJR1Y0WVcxd2JHVkFaWGhoYlhCc1pTNWpiMjBpWFN3aWJHOW5iMVZ5YVNJNkltaDBkSEJ6T2k4dlkyeHBaVzUwTG1WNFlXMXdiR1V1YjNKbkwyeHZaMjh1Y0c1bklpd2lkRzl6VlhKcElqb2lhSFIwY0hNNkx5OWpiR2xsYm5RdVpYaGhiWEJzWlM1dmNtY3ZkRzl6SWl3aWNHOXNhV041VlhKcElqb2lhSFIwY0hNNkx5OWpiR2xsYm5RdVpYaGhiWEJzWlM1dmNtY3ZjRzlzYVdONUluMC5rUjN3RVhVaXZUaU4zdTdTYmpIU1ZWTTRpblFydm5DS3Z4WHRVdG5GSHM5NS1IRUlBWEVqeG9sYlpVaTZPeF9EWlNwTWZkMXJ2QUJXWGhrYzlienBqSkRVVnNPcTlZZERuV290am5RU3ItVmhKaUFEVkQ3cjdOUGhORWJPLUhvYkdteWVKMW9waDdaalJFMzFwUFBKbC1feHVWazh4VFhKN1RzS21CSXJmcFhOVHBTZnQwbjBQMno1UVN5ZDJEZGRBMlJVVjBxUGZlRTBUQTd0SEszQzhqTEZwUmR2ZXVRelQyQlNLZFZ2VzZ5YzIyVGtCS1NyNWJEQ0RRSHJOal9zbEp1QTJhajkxdFpuZzVLYU44WGxXX0Z0cG5saFRXMUxNb0hpSHVOdU9DUW1OZFp0dnA2QTBkTnFfU2xwSGFZY003NXhFN0pNbUdyME9jeTJsdnktT3ciCn0=&state=client123
```

> Identification request
>
> Use parameter "state", the parameter state get back with response

## Response

```text
HTTP 302 Found
https://client.example.org/callback?salt=rrU94Nc3Z6gPBQV3&encryptedData=WR-euAw6XHge5iEPKjE66YTOOSuHir57kkI3Fb6FCE3OVIPBz9Kdcck5li6xaAUJQdy7Ih90v_LuHn7nHiGhHvgsh3Dj8wYKsmFS2PG4x73UD7843SIc5apwUhHEE_uR9iS9EB3CvwPty4y4YyniTTlJ5WSlyYg2DqXVbo3fi3lXArQG-pptuaMdbFj3uftXTdvdpWJZ5JJBNXizGg48YQYgUerajl9gx717Aki1ZsvNGw_IYC8oEMEFEfk-Rn2UToJ5pmuPgpdwGcCaF5z7_kxyknDVsr2p6ue4ypTqJheGdMIcXKQ-Vs2iq55AWR61k8TttvruPq4LfTbPk60xZX0xuveJG9kHvLu7k5WKDXcS-VX_SwFXYHrxFaa0DDOONT8rSmozQso_gB5rtR4Jlb2dbhvUg7pUG2nZMs8BSmOX_ry2dug7t8XYxxE9pdfTZb4KWzLzOh-MeDB-NcWRSg8fG4AXZV41sDLXlGVbGms5nwxOky5phvr8i2Ks-vx75OCBC6MCpL0d1sHI-8CSX-PEd7NzMiIbLuAWU0hAf461HlIqGJNdr9oFovpq7EZxy1bJyLXFhYTVP8rWjQZYixckEHhY7ElSiziJjLd3to8EqiAvWuzv2qEdzn_cmKYXWIWVT4L2AAswhmtHw_2G0tGvW-YXv5K_-ZMl8WGSECaw4v6CbyA8VerEiL0GOAaZSfdxzNez3mvsljs0rmH0KBU-pQWbY6MnNdxfXOuK_PeLQ01taU-1UVyr3t41aRNmBPk6pAlqFXGu3Z_rlvJjwGs6OT1OHQTi6OAeMVUQN5oPhCPHNZdkQ3LsxnMzaQ7WXqxNY2riC150ad0Wy1od1gKZuVToMLPAY6hu0fDxseZvKn64bGbRZ2ZUrd-cZ_ihDKm6pADwfg0Nv69O5SctWMYBeakihAIvIWb8083aySxhRlJ8tdPsgy3RB3PvpULA--JWmBiXtIBtHmg80TdMYYwxPOa319xblONIqAOSGnMW7QMlwfbmROsCNP9mSfgINkZKzRUWVyaJnPOJmAMMHya3AxGsK9ZD5zjZFaFcMThyWlTGCnOY5c5FtgBiuYbbiIBp0O9JDBIlI3NS4Q71e3uv3Wc6ipUZSzkaeGBXMt-yOS_56Gd3yrz7_Vgf5yHyVgGAKAyWnD7cIFvShts_bbT3oZzoS_ZxWSSucreTfjpQ0TXM7kXn
```

## Decrypt response

<details><summary>example java online</summary>

[online-java.com](https://www.online-java.com/hp3aP8K9bv)

</details>

<details><summary>example Java</summary>

[Source code on Github](https://github.com/komercka/adaa-example-spring-boot/blob/b24d79543d987d71183620e48806fcb48722d52c/core/src/main/java/cz/kb/openbanking/adaa/example/springboot/core/decryption/impl/Aes256DecryptionServiceImpl.java#L29)

</details>

<details><summary>example PHP</summary>

```php
<?php
// JSON property encryptionKey of registrationRequest, base64 encoded
$key = $encryptionKey = "Ri1KYU5kUmdVa1hwMnM1djh5L0I/RShIK0tiUGVTaFY=";
// GET parameter salt, base64url encoded
$initialization_vector = $salt = "xrvaINMLqotAbWRK";
// GET parameter encryptedData, base64url encoded
$ciphertext = $encryptedData = "RtGNAS-zQOxSB8W0HfqJjCoyt9KgImW_l-HjVC40hOOl-RNfRF3hzDIT1kvFVF8i_KX9XmqAftb6lyq-jLCEc_MSgqt3q1ixv3Ez4SbS3G5e3qGzLwxIMi2sCt00aDNwK2ipsJ4aw8s7ePPnl4oY-y1st9rwCWR0rrgEZwS9jmS4uJWGPn9K3jbKRnMslznDbtFLNJctMVXBTP-cv47JelxLCBOQSlK29rMuEFrhHR_VQrPq6gtZaBVSXZSYT0XOklp7nu9mVhrMCRtBCC5oiu5MPE5JYx4ANo3hUY7_NyQl2bpn9GfRXrdvqRGE-gy2upj-cDkm0t_tV8xmYge9DBQTH3B_4BGl2qTk_o-m7pEmKkS8XSdQhGcuFlykqrkE8SzB5I8esfzWOM0pwxbz0H_VaylKYHY=";

/**
 * Decodes data encoded as base64url.
 * @link https://tools.ietf.org/html/rfc4648#section-5
 * @param string $string The encoded data.
 * @return string|false the original data or false on failure. The returned data may be binary.
 */
function base64url_decode($string)
{
    return base64_decode(str_replace(array('-', '_'), array('+', '/'), $string));
}

/**
 * Decrypts ciphertext encrypted with standard java.base.javax.crypto.Cipher transformation AES/GCM/NoPadding into plaintext.
 * Assumes that authentication tag is appended to the ciphertext as documented in the link below.
 * @link https://docs.oracle.com/en/java/javase/11/docs/api/java.base/javax/crypto/Cipher.html
 * @param string $ciphertext_bytes The ciphertext as binary data.
 * @param string $initialization_vector_bytes The initialization vector as binary data.
 * @param string $key_bytes The key as binary data.
 * @return false|string The decrypted plaintext on success or false on failure.
 */
function decrypt_aes_256_gcm($ciphertext_bytes, $initialization_vector_bytes, $key_bytes)
{
    $cipher = "aes-256-gcm";
    $authentication_tag_length = 16;
    // separate data from authentication tag
    $data_bytes = substr($ciphertext_bytes, 0, -$authentication_tag_length);
    // separate authentication tag from data
    $authentication_tag_bytes = substr($ciphertext_bytes, -$authentication_tag_length);
    return openssl_decrypt($data_bytes, $cipher, $key_bytes, OPENSSL_RAW_DATA, $initialization_vector_bytes, $authentication_tag_bytes);
}

$plaintext = decrypt_aes_256_gcm(base64url_decode($ciphertext), base64url_decode($initialization_vector), base64_decode($key));
echo "plaintext:\n$plaintext";
?>

```

</details>

### Decrypted data

```json
{
  "application_type": "web",
  "redirect_uris": [
    "https://client.example.org/callback-backup",
    "https://client.example.org/callback"
  ],
  "client_name": "ExampleClient",
  "client_name#en-US": "ExampleClient",
  "logo_uri": "https://client.example.org/logo.png",
  "policy_uri": "https://client.example.org/policy",
  "tos_uri": "https://client.example.org/tos",
  "contact": "example@example.com",
  "contacts": ["example@example.com"],
  "scopes": ["adaa"],
  "scope": "adaa",
  "response_types": ["code"],
  "response_type": "code",
  "grant_types": ["refresh_token", "authorization_code"],
  "subject_type": "public",
  "token_endpoint_auth_method": "client_secret_basic",
  "require_auth_time": false,
  "bin": "123456",
  "client_id": "ExampleClient-6303",
  "client_secret": "bUfDQ1fMmfaSlZBZXlxBOQ",
  "api_key": "NOT_PROVIDED",
  "registration_client_uri": "https://caas.kb.cz/openam/json/caas/api/oauth2/register/ExampleClient-6303",
  "client_id_issued_at": 1649407196
}
```

# Authorization code

> Token validity
> Code has validity only 2 minutes

## Requests

```js
GET
https://api-gateway.kb.cz/sandbox/oauth2-authorization-ui/v2/?response_type=code&client_id=ExampleClient-6303&redirect_uri=http://localhost:8888/&scope=adaa%20card_data%20bpisp&state=xyz

```

## Response

```
HTTP 302 Found
https://localhost:8888/?code=eyJ1c2VySWQiOiJLbGllbnQgMSIsInNjb3BlcyI6WyJhZGFhIl19&state=xyz
```

# Refresh token

> Token validity
> refresh_token validity 12 months

## Request

```js
curl --location 'https://api-gateway.kb.cz/sandbox/oauth2/v2/access_token' \
--header 'x-correlation-id: 7696716b-a521-40ff-bdd7-2895d9ef12dd' \
--header 'apiKey: eyJ4NXQiOiJPVFl5T0RCa1l6YzNNemhpWkdVd05XWmpNemhqWlRsbU1EaGhPRFU0WVRJMk5qUTFPVE5sTkE9PSIsImtpZCI6InByb2RfYXBpbSIsInR5cCI6IkpXVCIsImFsZyI6IlJTMjU2In0=.eyJzdWIiOiJLQi1DVVNcL21pbG9zQHNvbnRhay5ldUBjYXJib24uc3VwZXIiLCJhcHBsaWNhdGlvbiI6eyJvd25lciI6IktCLUNVU1wvbWlsb3NAc29udGFrLmV1IiwidGllclF1b3RhVHlwZSI6bnVsbCwidGllciI6IlVubGltaXRlZCIsIm5hbWUiOiJPYXV0aDItc2FuZGJveF92Ml8xIiwiaWQiOjQzLCJ1dWlkIjoiNDJjMzMwNjgtMGRkNy00MDhlLTlmZDMtNWYwMzFhMDQ2NTBiIn0sImlzcyI6Imh0dHBzOlwvXC9hcGltLnByb2Qub2Itb3V0Ym91bmQua2JjbG91ZFwvb2F1dGgyXC90b2tlbiIsInRpZXJJbmZvIjp7IlVubGltaXRlZCI6eyJ0aWVyUXVvdGFUeXBlIjoicmVxdWVzdENvdW50IiwiZ3JhcGhRTE1heENvbXBsZXhpdHkiOjAsImdyYXBoUUxNYXhEZXB0aCI6MCwic3RvcE9uUXVvdGFSZWFjaCI6dHJ1ZSwic3Bpa2VBcnJlc3RMaW1pdCI6MCwic3Bpa2VBcnJlc3RVbml0IjpudWxsfX0sImtleXR5cGUiOiJQUk9EVUNUSU9OIiwic3Vic2NyaWJlZEFQSXMiOlt7InN1YnNjcmliZXJUZW5hbnREb21haW4iOiJjYXJib24uc3VwZXIiLCJuYW1lIjoiT2F1dGgyLXNhbmRib3giLCJjb250ZXh0IjoiXC9zYW5kYm94XC9vYXV0aDJcL3YyIiwicHVibGlzaGVyIjoiYWRtaW4iLCJ2ZXJzaW9uIjoidjIiLCJzdWJzY3JpcHRpb25UaWVyIjoiVW5saW1pdGVkIn1dLCJpYXQiOjE3MDIyODc1OTksImp0aSI6IjRjYWJiZDUyLTljZTEtNGE5ZS04NWU4LTQ2ZWY3NzljOTZlYiJ9.oUgd-Lv34mHQUGl0cZefeY9dGJmTVT2L5vtyvx3r7Yqc5mndvmhFCtaxgufvIyjMSFC29tf8dVBpHZWFdsCeCs1b2S9ElgPQddx2727Pp8mnCgjDNQ27HEpk6udwKypxHNPZuizk99NhcwK_7PXekM6wgs93cMe7oVeH5mMjL5jK1JdyaA_sIbQlgoXe0ATlkvBkXC-uIuMheug3u0Lskd9jbmqU6rZMXTS417T4TKXrKDufHjHoJICbFcsH6aabJB9hSeNg8D5Wi-8w3aWF9mWkfAjZU7FSZUkTWIz9_vTohefJGqb_buHb0eGxUXQlN093VTe2ySc-wcDbeVR53w==' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode 'redirect_uri=https://client.example.org/callback' \
--data-urlencode 'code=eyJ1c2VySWQiOiJ0ZXN0Iiwic2NvcGVzIjpbImFkYWEiXX0' \
--data-urlencode 'client_id=ExampleClient-6303' \
--data-urlencode 'client_secret=bUfDQ1fMmfaSlZBZXlxBOQ' \
--data-urlencode 'grant_type=authorization_code'
```

## Response

HTTP 200

```json
{
  "token_type": "Bearer",
  "access_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJLQklEPXRlc3QiLCJhdWRpdFRyYWNraW5nSWQiOiJkNzQxMmZlNS1mZTczLTQ5NDUtYjc5Yy0wYmFmMDEyNzEyNWQiLCJpc3MiOiJodHRwczovL2xvZ2luLmtiLmN6L29wZW5hbS9vYXV0aDIiLCJ0b2tlbk5hbWUiOiJhY2Nlc3NfdG9rZW4iLCJ0b2tlbl90eXBlIjoiQmVhcmVyIiwiYXV0aEdyYW50SWQiOiI2YWNjNzYxZS1hODZlLTRkYjUtODU4YS1kZTBmZmIzNDIzNDEiLCJhdWQiOiIxMjM1NDYiLCJuYmYiOjE2NzIzMTk5NTgsInNjb3BlIjpbImFkYWEiXSwicmVhbG0iOiIvIiwiZXhwIjoxNjcyMzIzNTU4LCJpYXQiOjE2NzIzMTk5NTgsImV4cGlyZXNfaW4iOjM2MDAwMDAsImp0aSI6IjE2NGNmZWE4LTQ2MGYtNDBjYS1hMTRjLWJlNTZjNmY1YjBjNiJ9.IsMZtCCnlhcgc7bcVi8WN9QyOgEcpP8_ckigEU9U_4w",
  "id_token": null,
  "refresh_token": "eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJLQklEPXRlc3QiLCJhdWRpdFRyYWNraW5nSWQiOiJkNzQxMmZlNS1mZTczLTQ5NDUtYjc5Yy0wYmFmMDEyNzEyNWQiLCJpc3MiOiJodHRwczovL2xvZ2luLmtiLmN6L29wZW5hbS9vYXV0aDIiLCJ0b2tlbk5hbWUiOiJyZWZyZXNoX3Rva2VuIiwidG9rZW5fdHlwZSI6IkJlYXJlciIsImF1dGhHcmFudElkIjoiNmFjYzc2MWUtYTg2ZS00ZGI1LTg1OGEtZGUwZmZiMzQyMzQxIiwiYXVkIjoiMTIzNTQ2IiwibmJmIjoxNjcyMzE5OTU4LCJzY29wZSI6WyJhZGFhIl0sInJlYWxtIjoiLyIsImV4cCI6MTY3MjMyMzU1OCwiaWF0IjoxNjcyMzE5OTU4LCJleHBpcmVzX2luIjozNjAwMDAwLCJqdGkiOiIxNjRjZmVhOC00NjBmLTQwY2EtYTE0Yy1iZTU2YzZmNWIwYzYifQ.t6wSrCs7uL7GW1JGe_9cgBz-iDhJCi3CADHsFZDnuDM",
  "expires_in": 3600,
  "acr": null
}
```

# Access token

> Token validity
>
> - access_token validity 3 minutes
> - access token is intended to be reused until the time of it's expiration
> - excessive requests to obtain a new access token may result in a status response `429 Too Many Requests`

## Request

```json
curl --location 'https://api-gateway.kb.cz/sandbox/oauth2/v2/access_token' \
--header 'x-correlation-id: 95f31a9a-6a57-47e8-9e46-6968e3cf1d2b' \
--header 'apiKey: eyJ4NXQiOiJPVFl5T0RCa1l6YzNNemhpWkdVd05XWmpNemhqWlRsbU1EaGhPRFU0WVRJMk5qUTFPVE5sTkE9PSIsImtpZCI6InByb2RfYXBpbSIsInR5cCI6IkpXVCIsImFsZyI6IlJTMjU2In0=.eyJzdWIiOiJLQi1DVVNcL21pbG9zQHNvbnRhay5ldUBjYXJib24uc3VwZXIiLCJhcHBsaWNhdGlvbiI6eyJvd25lciI6IktCLUNVU1wvbWlsb3NAc29udGFrLmV1IiwidGllclF1b3RhVHlwZSI6bnVsbCwidGllciI6IlVubGltaXRlZCIsIm5hbWUiOiJPYXV0aDItc2FuZGJveF92Ml8xIiwiaWQiOjQzLCJ1dWlkIjoiNDJjMzMwNjgtMGRkNy00MDhlLTlmZDMtNWYwMzFhMDQ2NTBiIn0sImlzcyI6Imh0dHBzOlwvXC9hcGltLnByb2Qub2Itb3V0Ym91bmQua2JjbG91ZFwvb2F1dGgyXC90b2tlbiIsInRpZXJJbmZvIjp7IlVubGltaXRlZCI6eyJ0aWVyUXVvdGFUeXBlIjoicmVxdWVzdENvdW50IiwiZ3JhcGhRTE1heENvbXBsZXhpdHkiOjAsImdyYXBoUUxNYXhEZXB0aCI6MCwic3RvcE9uUXVvdGFSZWFjaCI6dHJ1ZSwic3Bpa2VBcnJlc3RMaW1pdCI6MCwic3Bpa2VBcnJlc3RVbml0IjpudWxsfX0sImtleXR5cGUiOiJQUk9EVUNUSU9OIiwic3Vic2NyaWJlZEFQSXMiOlt7InN1YnNjcmliZXJUZW5hbnREb21haW4iOiJjYXJib24uc3VwZXIiLCJuYW1lIjoiT2F1dGgyLXNhbmRib3giLCJjb250ZXh0IjoiXC9zYW5kYm94XC9vYXV0aDJcL3YyIiwicHVibGlzaGVyIjoiYWRtaW4iLCJ2ZXJzaW9uIjoidjIiLCJzdWJzY3JpcHRpb25UaWVyIjoiVW5saW1pdGVkIn1dLCJpYXQiOjE3MDIyODc1OTksImp0aSI6IjRjYWJiZDUyLTljZTEtNGE5ZS04NWU4LTQ2ZWY3NzljOTZlYiJ9.oUgd-Lv34mHQUGl0cZefeY9dGJmTVT2L5vtyvx3r7Yqc5mndvmhFCtaxgufvIyjMSFC29tf8dVBpHZWFdsCeCs1b2S9ElgPQddx2727Pp8mnCgjDNQ27HEpk6udwKypxHNPZuizk99NhcwK_7PXekM6wgs93cMe7oVeH5mMjL5jK1JdyaA_sIbQlgoXe0ATlkvBkXC-uIuMheug3u0Lskd9jbmqU6rZMXTS417T4TKXrKDufHjHoJICbFcsH6aabJB9hSeNg8D5Wi-8w3aWF9mWkfAjZU7FSZUkTWIz9_vTohefJGqb_buHb0eGxUXQlN093VTe2ySc-wcDbeVR53w==' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode 'redirect_uri=https://client.example.org/callback' \
--data-urlencode 'client_id=ExampleClient-6303' \
--data-urlencode 'client_secret=bUfDQ1fMmfaSlZBZXlxBOQ' \
--data-urlencode 'refresh_token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJLQklEPXRlc3QiLCJhdWRpdFRyYWNraW5nSWQiOiJkNzQxMmZlNS1mZTczLTQ5NDUtYjc5Yy0wYmFmMDEyNzEyNWQiLCJpc3MiOiJodHRwczovL2xvZ2luLmtiLmN6L29wZW5hbS9vYXV0aDIiLCJ0b2tlbk5hbWUiOiJyZWZyZXNoX3Rva2VuIiwidG9rZW5fdHlwZSI6IkJlYXJlciIsImF1dGhHcmFudElkIjoiNmFjYzc2MWUtYTg2ZS00ZGI1LTg1OGEtZGUwZmZiMzQyMzQxIiwiYXVkIjoiMTIzNTQ2IiwibmJmIjoxNzAyMjg3OTk1LCJzY29wZSI6WyJhZGFhIl0sInJlYWxtIjoiLyIsImV4cCI6MTcwMjI5MTU5NSwiaWF0IjoxNzAyMjg3OTk1LCJleHBpcmVzX2luIjozNjAwMDAwLCJqdGkiOiIxNjRjZmVhOC00NjBmLTQwY2EtYTE0Yy1iZTU2YzZmNWIwYzYifQ.mTJZ7667jUDHQNGkXRQI8ti_rUtnCP3ya5saEVq-Rb4' \
--data-urlencode 'grant_type=refresh_token'
```

## Response

```json
{
  "access_token": "eyJ0eXAiOiJKV1QiLCJraWQiOiJ3RjJTa1I3NWMxamZsZ1VIOWJ6Wno3Tzllemc9IiwiYWxnIjoiUlMyNTYifQ.eyJzdWIiOiJBUElJRD01MmYwNDgyNjM3OTM0ZGZmOWY5MjE1MTBhMjlhMWYwYSIsImN0cyI6Ik9BVVRIMl9TVEFURUxFU1NfR1JBTlQiLCJhdXRoX2xldmVsIjo2LCJhdWRpdFRyYWNraW5nSWQiOiJmZjhkZTdlNy0xMGMxLTRiNzctYmY3Yy0xY2ZkMzYzMDI5MjItMzAyMzg4NzEiLCJpc3MiOiJodHRwczovL2NhYXMua2IuY3ovb3BlbmFtL29hdXRoMiIsInRva2VuTmFtZSI6ImFjY2Vzc190b2tlbiIsInRva2VuX3R5cGUiOiJCZWFyZXIiLCJhdXRoR3JhbnRJZCI6IjF1bzJ1ZHNjS0dLSWQwVjFFT2ZzRW1sUUtQcyIsImF1ZCI6IktpZmxpLTE2MzUiLCJuYmYiOjE2NTUzNzczNTUsImdyYW50X3R5cGUiOiJyZWZyZXNoX3Rva2VuIiwic2NvcGUiOlsiYWRhYSJdLCJhdXRoX3RpbWUiOjE2NTUzNzcyNzMsInJlYWxtIjoiLyIsImV4cCI6MTY1NTM3NzUzNSwiaWF0IjoxNjU1Mzc3MzU1LCJleHBpcmVzX2luIjoxODAsImp0aSI6IjVqN0d3U1ZWcXlzU0NoX1hoQmxMaUxTTV9MRSIsImNhYXNPcGVyYXRpb25JZCI6IjUyNzYyMTc3NmRiODQ0MTg5MGJjM2MzM2RkZjYzYmVlIn0.Dy_60fOTOclbNVR4gUybTV8XDdcyXxqZoQGoRZq5Ou0PDgJiDcYxKIUMvNQqtW06kEVgCCCvTzrwiVH8ArteCWGMBQnjANwgSm8LB8567tzKN4NxAar3TXSd55ZrDhbk1SbzJyaDnj9qMsIMf9a1u4H6JMeyAGA1MK6XehsJ70dZzN_R6YaB3hG5iMxUG_-z-_cTWs29rPAoFbRUGKuSzaXRyefmiS-pJXgshfoey4YF6swyI3K-MalkzgW1WzGxn7vRwjeQ5VyxNsDsygsjJ90qgcHNqvdglCyWAasMxxqE6CgfVv4J7Ym0fnu9HK0QyPNaUlQNwZ0QeXfSPBSFrg",
  "scope": "adaa",
  "token_type": "Bearer",
  "expires_in": 179
}
```

# Accounts

## Request

```bash
curl --location 'https://api-gateway.kb.cz/sandbox/adaa/v1/accounts' \
--header 'x-correlation-id: 5303a3ba-ec9e-4b41-841e-be60590e1b03' \
--header 'apiKey: eyJ4NXQiOiJPVFl5T0RCa1l6YzNNemhpWkdVd05XWmpNemhqWlRsbU1EaGhPRFU0WVRJMk5qUTFPVE5sTkE9PSIsImtpZCI6InByb2RfYXBpbSIsInR5cCI6IkpXVCIsImFsZyI6IlJTMjU2In0=.eyJzdWIiOiJLQi1DVVNcL21pbG9zQHNvbnRhay5ldUBjYXJib24uc3VwZXIiLCJhcHBsaWNhdGlvbiI6eyJvd25lciI6IktCLUNVU1wvbWlsb3NAc29udGFrLmV1IiwidGllclF1b3RhVHlwZSI6bnVsbCwidGllciI6IlVubGltaXRlZCIsIm5hbWUiOiJBY2NvdW50LURpcmVjdC1BY2Nlc3MtQVBJLVNhbmRib3hfdjFfMSIsImlkIjozNCwidXVpZCI6Ijk4ZjdlMjZlLTRlM2EtNDllNS1iOGJiLTU0YWRlNjEwZjJiOSJ9LCJpc3MiOiJodHRwczpcL1wvYXBpbS5wcm9kLm9iLW91dGJvdW5kLmtiY2xvdWRcL29hdXRoMlwvdG9rZW4iLCJ0aWVySW5mbyI6eyJVbmxpbWl0ZWQiOnsidGllclF1b3RhVHlwZSI6InJlcXVlc3RDb3VudCIsImdyYXBoUUxNYXhDb21wbGV4aXR5IjowLCJncmFwaFFMTWF4RGVwdGgiOjAsInN0b3BPblF1b3RhUmVhY2giOnRydWUsInNwaWtlQXJyZXN0TGltaXQiOjAsInNwaWtlQXJyZXN0VW5pdCI6bnVsbH19LCJrZXl0eXBlIjoiUFJPRFVDVElPTiIsInN1YnNjcmliZWRBUElzIjpbeyJzdWJzY3JpYmVyVGVuYW50RG9tYWluIjoiY2FyYm9uLnN1cGVyIiwibmFtZSI6IkFjY291bnQtRGlyZWN0LUFjY2Vzcy1BUEktU2FuZGJveCIsImNvbnRleHQiOiJcL3NhbmRib3hcL2FkYWFcL3YxIiwicHVibGlzaGVyIjoiYWRtaW4iLCJ2ZXJzaW9uIjoidjEiLCJzdWJzY3JpcHRpb25UaWVyIjoiVW5saW1pdGVkIn1dLCJpYXQiOjE3MDIyODc2NzksImp0aSI6ImRmMmNlY2M0LTNkNDItNDU3Ni1hY2E1LTk5ZDQ1YjVhZDEwYSJ9.fe2yTBFr_jKs1qhVIWzi2Qkfz9K0v3DhzU5vPS94rUMXaKOsdQK2ELjQO1kRuBlR4Y4NX66y5iVMxKEx53mAhSQmsIFaAo72Uhz3u9_FI4ytq8iBa1IU-QWNdL4Y5twmLl3uGK2mMDzItINtaIgAfK47h7r7IhMU1NYIUv_mJesjoqLq93D1QHdYIsfFav7MVU2K9QJSYWyDX0hbNZU28D0_FqbTvXRSAzHyk2uz_fv9xLZB-d5ZgIYOiz8VWvkJ6zTtrWzMEPD7Z4mbdhXrxLoc8IxUCo4N15kYwkEPAQIA0ZW_zN8d_4DPM2kRmMb1moLVcxgxzOCl5KsIYRX4HQ==' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJLQklEPXRlc3QiLCJhdWRpdFRyYWNraW5nSWQiOiJkNzQxMmZlNS1mZTczLTQ5NDUtYjc5Yy0wYmFmMDEyNzEyNWQiLCJpc3MiOiJodHRwczovL2xvZ2luLmtiLmN6L29wZW5hbS9vYXV0aDIiLCJ0b2tlbk5hbWUiOiJhY2Nlc3NfdG9rZW4iLCJ0b2tlbl90eXBlIjoiQmVhcmVyIiwiYXV0aEdyYW50SWQiOiI2YWNjNzYxZS1hODZlLTRkYjUtODU4YS1kZTBmZmIzNDIzNDEiLCJhdWQiOiIxMjM1NDYiLCJuYmYiOjE3MDIyODgxMDcsInNjb3BlIjpbImFkYWEiXSwicmVhbG0iOiIvIiwiZXhwIjoxNzAyMjkxNzA3LCJpYXQiOjE3MDIyODgxMDcsImV4cGlyZXNfaW4iOjM2MDAwMDAsImp0aSI6IjE2NGNmZWE4LTQ2MGYtNDBjYS1hMTRjLWJlNTZjNmY1YjBjNiJ9.iL-wV62DuWuTYbis48aakFCqZMSD01kNBRt_TLXkWcI'
```

## Response

HTTP 200

```json
[
  {
    "accountId": "Q1oxMzAxMDAwOTAxMTQ3NzcxODAwMjI3OkNaSw",
    "iban": "CZ1301000901147771800227",
    "currency": "CZK"
  },
  {
    "accountId": "Q1o2MTAxMDAwOTAwOTMwNzkwMTgwMjg3OkNaSw",
    "iban": "CZ6101000900930790180287",
    "currency": "CZK"
  },
  {
    "accountId": "Q1o0NDAxMDAwOTAxMTQ4MDk2MTMwMjI3OkNaSw",
    "iban": "CZ4401000901148096130227",
    "currency": "CZK"
  },
  {
    "accountId": "Q1o5NjAxMDAwOTAxMTQ4MDY2NTQwMjE3OkNaSw",
    "iban": "CZ9601000901148066540217",
    "currency": "CZK"
  },
  {
    "accountId": "Q1o2ODAxMDAwOTAxMTQ3ODI2NzAwMjY3OkNaSw",
    "iban": "CZ6801000901147826700267",
    "currency": "CZK"
  }
]
```

# Transaction history

## Request

```bash
curl --location 'https://api-gateway.kb.cz/sandbox/adaa/v1/accounts/Q1oxMzAxMDAwOTAxMTQ3NzcxODAwMjI3OkNaSw/transactions?fromDate=2023-01-30&toDate=2023-04-14&size=20&page=0' \
--header 'x-correlation-id: 5ae253e4-4fdb-4dc8-a46b-7ccaf0f27fca' \
--header 'apiKey: eyJ4NXQiOiJPVFl5T0RCa1l6YzNNemhpWkdVd05XWmpNemhqWlRsbU1EaGhPRFU0WVRJMk5qUTFPVE5sTkE9PSIsImtpZCI6InByb2RfYXBpbSIsInR5cCI6IkpXVCIsImFsZyI6IlJTMjU2In0=.eyJzdWIiOiJLQi1DVVNcL21pbG9zQHNvbnRhay5ldUBjYXJib24uc3VwZXIiLCJhcHBsaWNhdGlvbiI6eyJvd25lciI6IktCLUNVU1wvbWlsb3NAc29udGFrLmV1IiwidGllclF1b3RhVHlwZSI6bnVsbCwidGllciI6IlVubGltaXRlZCIsIm5hbWUiOiJBY2NvdW50LURpcmVjdC1BY2Nlc3MtQVBJLVNhbmRib3hfdjFfMSIsImlkIjozNCwidXVpZCI6Ijk4ZjdlMjZlLTRlM2EtNDllNS1iOGJiLTU0YWRlNjEwZjJiOSJ9LCJpc3MiOiJodHRwczpcL1wvYXBpbS5wcm9kLm9iLW91dGJvdW5kLmtiY2xvdWRcL29hdXRoMlwvdG9rZW4iLCJ0aWVySW5mbyI6eyJVbmxpbWl0ZWQiOnsidGllclF1b3RhVHlwZSI6InJlcXVlc3RDb3VudCIsImdyYXBoUUxNYXhDb21wbGV4aXR5IjowLCJncmFwaFFMTWF4RGVwdGgiOjAsInN0b3BPblF1b3RhUmVhY2giOnRydWUsInNwaWtlQXJyZXN0TGltaXQiOjAsInNwaWtlQXJyZXN0VW5pdCI6bnVsbH19LCJrZXl0eXBlIjoiUFJPRFVDVElPTiIsInN1YnNjcmliZWRBUElzIjpbeyJzdWJzY3JpYmVyVGVuYW50RG9tYWluIjoiY2FyYm9uLnN1cGVyIiwibmFtZSI6IkFjY291bnQtRGlyZWN0LUFjY2Vzcy1BUEktU2FuZGJveCIsImNvbnRleHQiOiJcL3NhbmRib3hcL2FkYWFcL3YxIiwicHVibGlzaGVyIjoiYWRtaW4iLCJ2ZXJzaW9uIjoidjEiLCJzdWJzY3JpcHRpb25UaWVyIjoiVW5saW1pdGVkIn1dLCJpYXQiOjE3MDIyODc2NzksImp0aSI6ImRmMmNlY2M0LTNkNDItNDU3Ni1hY2E1LTk5ZDQ1YjVhZDEwYSJ9.fe2yTBFr_jKs1qhVIWzi2Qkfz9K0v3DhzU5vPS94rUMXaKOsdQK2ELjQO1kRuBlR4Y4NX66y5iVMxKEx53mAhSQmsIFaAo72Uhz3u9_FI4ytq8iBa1IU-QWNdL4Y5twmLl3uGK2mMDzItINtaIgAfK47h7r7IhMU1NYIUv_mJesjoqLq93D1QHdYIsfFav7MVU2K9QJSYWyDX0hbNZU28D0_FqbTvXRSAzHyk2uz_fv9xLZB-d5ZgIYOiz8VWvkJ6zTtrWzMEPD7Z4mbdhXrxLoc8IxUCo4N15kYwkEPAQIA0ZW_zN8d_4DPM2kRmMb1moLVcxgxzOCl5KsIYRX4HQ==' \
--header 'Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJLQklEPXRlc3QiLCJhdWRpdFRyYWNraW5nSWQiOiJkNzQxMmZlNS1mZTczLTQ5NDUtYjc5Yy0wYmFmMDEyNzEyNWQiLCJpc3MiOiJodHRwczovL2xvZ2luLmtiLmN6L29wZW5hbS9vYXV0aDIiLCJ0b2tlbk5hbWUiOiJhY2Nlc3NfdG9rZW4iLCJ0b2tlbl90eXBlIjoiQmVhcmVyIiwiYXV0aEdyYW50SWQiOiI2YWNjNzYxZS1hODZlLTRkYjUtODU4YS1kZTBmZmIzNDIzNDEiLCJhdWQiOiIxMjM1NDYiLCJuYmYiOjE3MDIyODgxMDcsInNjb3BlIjpbImFkYWEiXSwicmVhbG0iOiIvIiwiZXhwIjoxNzAyMjkxNzA3LCJpYXQiOjE3MDIyODgxMDcsImV4cGlyZXNfaW4iOjM2MDAwMDAsImp0aSI6IjE2NGNmZWE4LTQ2MGYtNDBjYS1hMTRjLWJlNTZjNmY1YjBjNiJ9.iL-wV62DuWuTYbis48aakFCqZMSD01kNBRt_TLXkWcI'
```

HTTP 200

## Response

```json
{
  "content": [
    {
      "lastUpdated": "2019-06-05T11:34:00Z",
      "accountType": "KB",
      "entryReference": "298-05062019 16020106916F1",
      "iban": "CZ1301000901147771800227",
      "creditDebitIndicator": "DEBIT",
      "transactionType": "FEE",
      "bankTransactionCode": {
        "code": "400006",
        "issuer": "OTHER"
      },
      "amount": {
        "value": 18.0,
        "currency": "CZK"
      },
      "bookingDate": "2019-06-05",
      "valueDate": "2019-06-05",
      "instructed": {
        "value": 18.0,
        "currency": "CZK"
      },
      "status": "PNG",
      "references": {
        "accountServicer": "298-05062019 16020106916F1",
        "constant": "0898"
      },
      "additionalTransactionInformation": "TP zalozeni :  1 x  18, F00106916F1TP_MBB"
    },
    {
      "lastUpdated": "2019-06-05T11:34:00Z",
      "accountType": "KB",
      "entryReference": "001-04062019 1602 602003 110031",
      "iban": "CZ1301000901147771800227",
      "creditDebitIndicator": "DEBIT",
      "transactionType": "DOMESTIC",
      "bankTransactionCode": {
        "code": "100001",
        "issuer": "OTHER"
      },
      "amount": {
        "value": 268.0,
        "currency": "CZK"
      },
      "bookingDate": "2019-06-04",
      "valueDate": "2019-06-04",
      "instructed": {
        "value": 268.0,
        "currency": "CZK"
      },
      "status": "BOOK",
      "counterParty": {
        "iban": "CZ0203000000000000000246",
        "accountNo": "0000000000000246",
        "bankBic": "CEKOCZPPXXX",
        "bankCode": "0300"
      },
      "references": {
        "accountServicer": "IU01RFIQT2F",
        "variable": "6112047021",
        "constant": "8422",
        "specific": "3258999654"
      },
      "additionalTransactionInformation": "Force pay debit, IU01RFIQT2F 01"
    },
    {
      "lastUpdated": "2019-06-05T11:34:00Z",
      "accountType": "KB",
      "entryReference": "001-22052019 1602 602030 390281",
      "iban": "CZ1301000901147771800227",
      "creditDebitIndicator": "CREDIT",
      "transactionType": "DOMESTIC",
      "bankTransactionCode": {
        "code": "100001",
        "issuer": "OTHER"
      },
      "amount": {
        "value": 2550.0,
        "currency": "CZK"
      },
      "bookingDate": "2019-05-22",
      "valueDate": "2019-05-22",
      "instructed": {
        "value": 2550.0,
        "currency": "CZK"
      },
      "status": "BOOK",
      "counterParty": {
        "iban": "CZ8101000901147770990217",
        "name": "TATOR JAN",
        "accountNo": "0901147770990217",
        "bankBic": "KOMBCZPPXXX",
        "bankCode": "0100"
      },
      "references": {
        "accountServicer": "IU01RFH4XQH"
      },
      "additionalTransactionInformation": "Transfer credit, IU01RFH4XQH 01"
    },
    {
      "lastUpdated": "2019-06-05T11:34:00Z",
      "accountType": "KB",
      "entryReference": "000-10052019-005-005-001-025660",
      "iban": "CZ1301000901147771800227",
      "creditDebitIndicator": "DEBIT",
      "transactionType": "DOMESTIC",
      "bankTransactionCode": {
        "code": "100001",
        "issuer": "OTHER"
      },
      "amount": {
        "value": 6669.0,
        "currency": "CZK"
      },
      "bookingDate": "2019-05-10",
      "valueDate": "2019-05-10",
      "instructed": {
        "value": 6669.0,
        "currency": "CZK"
      },
      "status": "BOOK",
      "counterParty": {
        "iban": "CZ5501000000000000000246",
        "name": "IB-TĚST-1-ALĚNA-ŠČŘP ALĚNKA",
        "accountNo": "0000000000000246",
        "bankBic": "CEKOCZPPXXX",
        "bankCode": "0100"
      },
      "references": {
        "accountServicer": "000-10052019-005-005-001-025660",
        "variable": "5545005500",
        "constant": "4564",
        "specific": "0000847552"
      },
      "additionalTransactionInformation": "Debit transfer, NA   CK-0000000000000246"
    },
    {
      "lastUpdated": "2019-06-05T11:34:00Z",
      "accountType": "KB",
      "entryReference": "001-01112021 1602 602005 011151",
      "iban": "CZ1301000901147771800227",
      "creditDebitIndicator": "CREDIT",
      "transactionType": "SEPA",
      "bankTransactionCode": {
        "code": "100004",
        "issuer": "OTHER"
      },
      "amount": {
        "value": 681.81,
        "currency": "CZK"
      },
      "bookingDate": "2019-05-25",
      "valueDate": "2019-05-25",
      "instructed": {
        "value": 27.28,
        "currency": "EUR"
      },
      "status": "BOOK",
      "counterParty": {
        "iban": "FR7630003033000002054269605",
        "name": "Francouzska Alizeé",
        "accountNo": "00020542696",
        "bankBic": "SOGEFRPPXXX",
        "bankCode": "30003"
      },
      "references": {
        "accountServicer": "IU01RFYZ35C",
        "endToEndIdentification": "a6s51f6s51a69",
        "constant": "6020000000",
        "specific": "2206139812",
        "receiver": "remittance info"
      },
      "additionalTransactionInformation": "Transfer credit, ucetFR7630003033000002054269605    rfKB   2206139812602               rfJUs65f1a6s5f1as561f651s9, bankSOGEFRPPXXX                    poplSLV, IU01RFYZ35C 13"
    }
  ],
  "totalPages": 1,
  "pageNumber": 0,
  "pageSize": 20,
  "numberOfElements": 5,
  "first": true,
  "last": true,
  "empty": false
}
```

# Subscribe notification

## Request

```js
curl --location 'https://api-gateway.kb.cz/sandbox/adaa/v1/accounts/Q1oxMzAxMDAwOTAxMTQ3NzcxODAwMjI3OkNaSw/transactions/event-subscriptions' \
--header 'x-correlation-id: 748697a2-a840-4e01-87a6-d249415859bf' \
--header 'apiKey: eyJ4NXQiOiJPVFl5T0RCa1l6YzNNemhpWkdVd05XWmpNemhqWlRsbU1EaGhPRFU0WVRJMk5qUTFPVE5sTkE9PSIsImtpZCI6InByb2RfYXBpbSIsInR5cCI6IkpXVCIsImFsZyI6IlJTMjU2In0=.eyJzdWIiOiJLQi1DVVNcL21pbG9zQHNvbnRhay5ldUBjYXJib24uc3VwZXIiLCJhcHBsaWNhdGlvbiI6eyJvd25lciI6IktCLUNVU1wvbWlsb3NAc29udGFrLmV1IiwidGllclF1b3RhVHlwZSI6bnVsbCwidGllciI6IlVubGltaXRlZCIsIm5hbWUiOiJBY2NvdW50LURpcmVjdC1BY2Nlc3MtQVBJLVNhbmRib3hfdjFfMSIsImlkIjozNCwidXVpZCI6Ijk4ZjdlMjZlLTRlM2EtNDllNS1iOGJiLTU0YWRlNjEwZjJiOSJ9LCJpc3MiOiJodHRwczpcL1wvYXBpbS5wcm9kLm9iLW91dGJvdW5kLmtiY2xvdWRcL29hdXRoMlwvdG9rZW4iLCJ0aWVySW5mbyI6eyJVbmxpbWl0ZWQiOnsidGllclF1b3RhVHlwZSI6InJlcXVlc3RDb3VudCIsImdyYXBoUUxNYXhDb21wbGV4aXR5IjowLCJncmFwaFFMTWF4RGVwdGgiOjAsInN0b3BPblF1b3RhUmVhY2giOnRydWUsInNwaWtlQXJyZXN0TGltaXQiOjAsInNwaWtlQXJyZXN0VW5pdCI6bnVsbH19LCJrZXl0eXBlIjoiUFJPRFVDVElPTiIsInN1YnNjcmliZWRBUElzIjpbeyJzdWJzY3JpYmVyVGVuYW50RG9tYWluIjoiY2FyYm9uLnN1cGVyIiwibmFtZSI6IkFjY291bnQtRGlyZWN0LUFjY2Vzcy1BUEktU2FuZGJveCIsImNvbnRleHQiOiJcL3NhbmRib3hcL2FkYWFcL3YxIiwicHVibGlzaGVyIjoiYWRtaW4iLCJ2ZXJzaW9uIjoidjEiLCJzdWJzY3JpcHRpb25UaWVyIjoiVW5saW1pdGVkIn1dLCJpYXQiOjE3MDIyODc2NzksImp0aSI6ImRmMmNlY2M0LTNkNDItNDU3Ni1hY2E1LTk5ZDQ1YjVhZDEwYSJ9.fe2yTBFr_jKs1qhVIWzi2Qkfz9K0v3DhzU5vPS94rUMXaKOsdQK2ELjQO1kRuBlR4Y4NX66y5iVMxKEx53mAhSQmsIFaAo72Uhz3u9_FI4ytq8iBa1IU-QWNdL4Y5twmLl3uGK2mMDzItINtaIgAfK47h7r7IhMU1NYIUv_mJesjoqLq93D1QHdYIsfFav7MVU2K9QJSYWyDX0hbNZU28D0_FqbTvXRSAzHyk2uz_fv9xLZB-d5ZgIYOiz8VWvkJ6zTtrWzMEPD7Z4mbdhXrxLoc8IxUCo4N15kYwkEPAQIA0ZW_zN8d_4DPM2kRmMb1moLVcxgxzOCl5KsIYRX4HQ==' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJLQklEPXRlc3QiLCJhdWRpdFRyYWNraW5nSWQiOiJkNzQxMmZlNS1mZTczLTQ5NDUtYjc5Yy0wYmFmMDEyNzEyNWQiLCJpc3MiOiJodHRwczovL2xvZ2luLmtiLmN6L29wZW5hbS9vYXV0aDIiLCJ0b2tlbk5hbWUiOiJhY2Nlc3NfdG9rZW4iLCJ0b2tlbl90eXBlIjoiQmVhcmVyIiwiYXV0aEdyYW50SWQiOiI2YWNjNzYxZS1hODZlLTRkYjUtODU4YS1kZTBmZmIzNDIzNDEiLCJhdWQiOiIxMjM1NDYiLCJuYmYiOjE3MDIyODgxMDcsInNjb3BlIjpbImFkYWEiXSwicmVhbG0iOiIvIiwiZXhwIjoxNzAyMjkxNzA3LCJpYXQiOjE3MDIyODgxMDcsImV4cGlyZXNfaW4iOjM2MDAwMDAsImp0aSI6IjE2NGNmZWE4LTQ2MGYtNDBjYS1hMTRjLWJlNTZjNmY1YjBjNiJ9.iL-wV62DuWuTYbis48aakFCqZMSD01kNBRt_TLXkWcI' \
--data '{
  "eventApiUrl": "https://company.org/event-api/v1",
  "eventApiKey": "no-valid"
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
curl --location 'https://api-gateway.kb.cz/sandbox/adaa/v1/accounts/Q1oxMzAxMDAwOTAxMTQ3NzcxODAwMjI3OkNaSw/transactions/event-subscriptions/11ba81e1-412e-4699-886a-d2268a7cb3f6' \
--header 'x-correlation-id: fce21329-2602-4977-b171-0c36e57b6043' \
--header 'apiKey: eyJ4NXQiOiJPVFl5T0RCa1l6YzNNemhpWkdVd05XWmpNemhqWlRsbU1EaGhPRFU0WVRJMk5qUTFPVE5sTkE9PSIsImtpZCI6InByb2RfYXBpbSIsInR5cCI6IkpXVCIsImFsZyI6IlJTMjU2In0=.eyJzdWIiOiJLQi1DVVNcL21pbG9zQHNvbnRhay5ldUBjYXJib24uc3VwZXIiLCJhcHBsaWNhdGlvbiI6eyJvd25lciI6IktCLUNVU1wvbWlsb3NAc29udGFrLmV1IiwidGllclF1b3RhVHlwZSI6bnVsbCwidGllciI6IlVubGltaXRlZCIsIm5hbWUiOiJBY2NvdW50LURpcmVjdC1BY2Nlc3MtQVBJLVNhbmRib3hfdjFfMSIsImlkIjozNCwidXVpZCI6Ijk4ZjdlMjZlLTRlM2EtNDllNS1iOGJiLTU0YWRlNjEwZjJiOSJ9LCJpc3MiOiJodHRwczpcL1wvYXBpbS5wcm9kLm9iLW91dGJvdW5kLmtiY2xvdWRcL29hdXRoMlwvdG9rZW4iLCJ0aWVySW5mbyI6eyJVbmxpbWl0ZWQiOnsidGllclF1b3RhVHlwZSI6InJlcXVlc3RDb3VudCIsImdyYXBoUUxNYXhDb21wbGV4aXR5IjowLCJncmFwaFFMTWF4RGVwdGgiOjAsInN0b3BPblF1b3RhUmVhY2giOnRydWUsInNwaWtlQXJyZXN0TGltaXQiOjAsInNwaWtlQXJyZXN0VW5pdCI6bnVsbH19LCJrZXl0eXBlIjoiUFJPRFVDVElPTiIsInN1YnNjcmliZWRBUElzIjpbeyJzdWJzY3JpYmVyVGVuYW50RG9tYWluIjoiY2FyYm9uLnN1cGVyIiwibmFtZSI6IkFjY291bnQtRGlyZWN0LUFjY2Vzcy1BUEktU2FuZGJveCIsImNvbnRleHQiOiJcL3NhbmRib3hcL2FkYWFcL3YxIiwicHVibGlzaGVyIjoiYWRtaW4iLCJ2ZXJzaW9uIjoidjEiLCJzdWJzY3JpcHRpb25UaWVyIjoiVW5saW1pdGVkIn1dLCJpYXQiOjE3MDIyODc2NzksImp0aSI6ImRmMmNlY2M0LTNkNDItNDU3Ni1hY2E1LTk5ZDQ1YjVhZDEwYSJ9.fe2yTBFr_jKs1qhVIWzi2Qkfz9K0v3DhzU5vPS94rUMXaKOsdQK2ELjQO1kRuBlR4Y4NX66y5iVMxKEx53mAhSQmsIFaAo72Uhz3u9_FI4ytq8iBa1IU-QWNdL4Y5twmLl3uGK2mMDzItINtaIgAfK47h7r7IhMU1NYIUv_mJesjoqLq93D1QHdYIsfFav7MVU2K9QJSYWyDX0hbNZU28D0_FqbTvXRSAzHyk2uz_fv9xLZB-d5ZgIYOiz8VWvkJ6zTtrWzMEPD7Z4mbdhXrxLoc8IxUCo4N15kYwkEPAQIA0ZW_zN8d_4DPM2kRmMb1moLVcxgxzOCl5KsIYRX4HQ==' \
--header 'Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJLQklEPXRlc3QiLCJhdWRpdFRyYWNraW5nSWQiOiJkNzQxMmZlNS1mZTczLTQ5NDUtYjc5Yy0wYmFmMDEyNzEyNWQiLCJpc3MiOiJodHRwczovL2xvZ2luLmtiLmN6L29wZW5hbS9vYXV0aDIiLCJ0b2tlbk5hbWUiOiJhY2Nlc3NfdG9rZW4iLCJ0b2tlbl90eXBlIjoiQmVhcmVyIiwiYXV0aEdyYW50SWQiOiI2YWNjNzYxZS1hODZlLTRkYjUtODU4YS1kZTBmZmIzNDIzNDEiLCJhdWQiOiIxMjM1NDYiLCJuYmYiOjE3MDIyODgxMDcsInNjb3BlIjpbImFkYWEiXSwicmVhbG0iOiIvIiwiZXhwIjoxNzAyMjkxNzA3LCJpYXQiOjE3MDIyODgxMDcsImV4cGlyZXNfaW4iOjM2MDAwMDAsImp0aSI6IjE2NGNmZWE4LTQ2MGYtNDBjYS1hMTRjLWJlNTZjNmY1YjBjNiJ9.iL-wV62DuWuTYbis48aakFCqZMSD01kNBRt_TLXkWcI''
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
curl --location --request DELETE 'https://api.kb.cz/open/api/sandbox/adaa/v1/accounts/Q1oxMzAxMDAwOTAxMTQ3NzcxODAwMjI3OkNaSwQ/transactions/event-subscriptions/622f2380-abd7-43aa-9a20-1a32a80b726d' \
--header 'x-correlation-id: 7640f544-7121-4805-96c6-a4879593cdc7' \
--header 'apiKey: Bearer b0bde4c0-0a13-329e-a1e8-95beff0a7905' \
--header 'Authorization: Bearer eyJ0eXAiOiJKV1QiLCJraWQiOiJ3RjJTa1I3NWMxamZsZ1VIOWJ6Wno3Tzllemc9IiwiYWxnIjoiUlMyNTYifQ.eyJzdWIiOiJBUElJRD01MmYwNDgyNjM3OTM0ZGZmOWY5MjE1MTBhMjlhMWYwYSIsImN0cyI6Ik9BVVRIMl9TVEFURUxFU1NfR1JBTlQiLCJhdXRoX2xldmVsIjo2LCJhdWRpdFRyYWNraW5nSWQiOiIxYTAwMDU3ZS02YzJjLTRmZmYtODRlZS04ZDU1MzE5OTgzYTAtNTgxNDczNTYiLCJpc3MiOiJodHRwczovL2NhYXMua2IuY3ovb3BlbmFtL29hdXRoMiIsInRva2VuTmFtZSI6ImFjY2Vzc190b2tlbiIsInRva2VuX3R5cGUiOiJCZWFyZXIiLCJhdXRoR3JhbnRJZCI6IjF1bzJ1ZHNjS0dLSWQwVjFFT2ZzRW1sUUtQcyIsImF1ZCI6IktpZmxpLTE2MzUiLCJuYmYiOjE2NTU5NzMzNzAsImdyYW50X3R5cGUiOiJyZWZyZXNoX3Rva2VuIiwic2NvcGUiOlsiYWRhYSJdLCJhdXRoX3RpbWUiOjE2NTUzNzcyNzMsInJlYWxtIjoiLyIsImV4cCI6MTY1NTk3MzU1MCwiaWF0IjoxNjU1OTczMzcwLCJleHBpcmVzX2luIjoxODAsImp0aSI6IjR6dmhxQzRheWVkakw0WWxCc05aUm90MF9hRSIsImNhYXNPcGVyYXRpb25JZCI6IjUyNzYyMTc3NmRiODQ0MTg5MGJjM2MzM2RkZjYzYmVlIn0.nG4gliOMVWbadIAWChglg2yQcqNocgF5-z0ehNIE4Y--C63Wr4sonLpCPJPwvlm1Tb3z10HxN1TUwmvDUHvZwKiomAaa9MRzmr4-oJwc8cr_K1b3dB6FeN6r01WH6RHTLK0I-WAEONZR7kmaZP4jNPB_jVNR4Lx_6vVqNsoo2PApXzMx1DAFZQsNy5JIryGuN2GA6B9LF3XqpN6o-BpKnNn9Dsj8T0QiVK716ChSU1BM3l7MpCulfzRhEzhJB3as5GKE0z8RguBibKMw88oU8WT3jBeaHEQnRaGaKc0MrMnSoT2BlG42vekXqDEhu-42Of_Y7VKgsFbk8HolOztwHQ'
```

## Response

HTTP 204

# Your API to receive notification

- [specification](https://github.com/komercka/adaa-eventapi-spring-boot-example/blob/master/rest/src/main/resources/openapi/adaa-event-api.yaml)
- if you want to limit network traffic, incoming requests from the bank come from IP addresses:
  - 194.50.202.179
  - 194.50.226.179

# Statements - List of statements

## Request

```js
curl --location 'https://api-gateway.kb.cz/sandbox/adaa/v1/accounts/Q1oxMzAxMDAwOTAxMTQ3NzcxODAwMjI3OkNaSw/statements/?dateFrom=2021-03-30T15%3A42%3A30.000Z' \
--header 'x-correlation-id: f0a91240-1c7b-492b-bb6a-f1712bb4ef46' \
--header 'apiKey: eyJ4NXQiOiJPVFl5T0RCa1l6YzNNemhpWkdVd05XWmpNemhqWlRsbU1EaGhPRFU0WVRJMk5qUTFPVE5sTkE9PSIsImtpZCI6InByb2RfYXBpbSIsInR5cCI6IkpXVCIsImFsZyI6IlJTMjU2In0=.eyJzdWIiOiJLQi1DVVNcL21pbG9zQHNvbnRhay5ldUBjYXJib24uc3VwZXIiLCJhcHBsaWNhdGlvbiI6eyJvd25lciI6IktCLUNVU1wvbWlsb3NAc29udGFrLmV1IiwidGllclF1b3RhVHlwZSI6bnVsbCwidGllciI6IlVubGltaXRlZCIsIm5hbWUiOiJBY2NvdW50LURpcmVjdC1BY2Nlc3MtQVBJLVNhbmRib3hfdjFfMSIsImlkIjozNCwidXVpZCI6Ijk4ZjdlMjZlLTRlM2EtNDllNS1iOGJiLTU0YWRlNjEwZjJiOSJ9LCJpc3MiOiJodHRwczpcL1wvYXBpbS5wcm9kLm9iLW91dGJvdW5kLmtiY2xvdWRcL29hdXRoMlwvdG9rZW4iLCJ0aWVySW5mbyI6eyJVbmxpbWl0ZWQiOnsidGllclF1b3RhVHlwZSI6InJlcXVlc3RDb3VudCIsImdyYXBoUUxNYXhDb21wbGV4aXR5IjowLCJncmFwaFFMTWF4RGVwdGgiOjAsInN0b3BPblF1b3RhUmVhY2giOnRydWUsInNwaWtlQXJyZXN0TGltaXQiOjAsInNwaWtlQXJyZXN0VW5pdCI6bnVsbH19LCJrZXl0eXBlIjoiUFJPRFVDVElPTiIsInN1YnNjcmliZWRBUElzIjpbeyJzdWJzY3JpYmVyVGVuYW50RG9tYWluIjoiY2FyYm9uLnN1cGVyIiwibmFtZSI6IkFjY291bnQtRGlyZWN0LUFjY2Vzcy1BUEktU2FuZGJveCIsImNvbnRleHQiOiJcL3NhbmRib3hcL2FkYWFcL3YxIiwicHVibGlzaGVyIjoiYWRtaW4iLCJ2ZXJzaW9uIjoidjEiLCJzdWJzY3JpcHRpb25UaWVyIjoiVW5saW1pdGVkIn1dLCJpYXQiOjE3MDIyODc2NzksImp0aSI6ImRmMmNlY2M0LTNkNDItNDU3Ni1hY2E1LTk5ZDQ1YjVhZDEwYSJ9.fe2yTBFr_jKs1qhVIWzi2Qkfz9K0v3DhzU5vPS94rUMXaKOsdQK2ELjQO1kRuBlR4Y4NX66y5iVMxKEx53mAhSQmsIFaAo72Uhz3u9_FI4ytq8iBa1IU-QWNdL4Y5twmLl3uGK2mMDzItINtaIgAfK47h7r7IhMU1NYIUv_mJesjoqLq93D1QHdYIsfFav7MVU2K9QJSYWyDX0hbNZU28D0_FqbTvXRSAzHyk2uz_fv9xLZB-d5ZgIYOiz8VWvkJ6zTtrWzMEPD7Z4mbdhXrxLoc8IxUCo4N15kYwkEPAQIA0ZW_zN8d_4DPM2kRmMb1moLVcxgxzOCl5KsIYRX4HQ==' \
--header 'Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJLQklEPXRlc3QiLCJhdWRpdFRyYWNraW5nSWQiOiJkNzQxMmZlNS1mZTczLTQ5NDUtYjc5Yy0wYmFmMDEyNzEyNWQiLCJpc3MiOiJodHRwczovL2xvZ2luLmtiLmN6L29wZW5hbS9vYXV0aDIiLCJ0b2tlbk5hbWUiOiJhY2Nlc3NfdG9rZW4iLCJ0b2tlbl90eXBlIjoiQmVhcmVyIiwiYXV0aEdyYW50SWQiOiI2YWNjNzYxZS1hODZlLTRkYjUtODU4YS1kZTBmZmIzNDIzNDEiLCJhdWQiOiIxMjM1NDYiLCJuYmYiOjE3MDIyODgxMDcsInNjb3BlIjpbImFkYWEiXSwicmVhbG0iOiIvIiwiZXhwIjoxNzAyMjkxNzA3LCJpYXQiOjE3MDIyODgxMDcsImV4cGlyZXNfaW4iOjM2MDAwMDAsImp0aSI6IjE2NGNmZWE4LTQ2MGYtNDBjYS1hMTRjLWJlNTZjNmY1YjBjNiJ9.iL-wV62DuWuTYbis48aakFCqZMSD01kNBRt_TLXkWcI'
```

## Response

```js
[
  {
    issued: "2022-04-07",
    sequenceNumber: 4,
    pagesCount: 1,
    statementId: 322640901,
    archive: false,
  },
  {
    issued: "2022-03-07",
    sequenceNumber: 3,
    pagesCount: 1,
    statementId: 325723851,
    archive: true,
  },
];
```

# Statements - Download file

## Request

```bash
curl --location 'https://api-gateway.kb.cz/sandbox/adaa/v1/accounts/Q1oxMzAxMDAwOTAxMTQ3NzcxODAwMjI3OkNaSw/statements/1132?dateFrom=2021-03-30T15%3A42%3A30.000Z' \
--header 'x-correlation-id: 82501558-a321-4ecb-a9b9-dcf824858128' \
--header 'apiKey: eyJ4NXQiOiJPVFl5T0RCa1l6YzNNemhpWkdVd05XWmpNemhqWlRsbU1EaGhPRFU0WVRJMk5qUTFPVE5sTkE9PSIsImtpZCI6InByb2RfYXBpbSIsInR5cCI6IkpXVCIsImFsZyI6IlJTMjU2In0=.eyJzdWIiOiJLQi1DVVNcL21pbG9zQHNvbnRhay5ldUBjYXJib24uc3VwZXIiLCJhcHBsaWNhdGlvbiI6eyJvd25lciI6IktCLUNVU1wvbWlsb3NAc29udGFrLmV1IiwidGllclF1b3RhVHlwZSI6bnVsbCwidGllciI6IlVubGltaXRlZCIsIm5hbWUiOiJBY2NvdW50LURpcmVjdC1BY2Nlc3MtQVBJLVNhbmRib3hfdjFfMSIsImlkIjozNCwidXVpZCI6Ijk4ZjdlMjZlLTRlM2EtNDllNS1iOGJiLTU0YWRlNjEwZjJiOSJ9LCJpc3MiOiJodHRwczpcL1wvYXBpbS5wcm9kLm9iLW91dGJvdW5kLmtiY2xvdWRcL29hdXRoMlwvdG9rZW4iLCJ0aWVySW5mbyI6eyJVbmxpbWl0ZWQiOnsidGllclF1b3RhVHlwZSI6InJlcXVlc3RDb3VudCIsImdyYXBoUUxNYXhDb21wbGV4aXR5IjowLCJncmFwaFFMTWF4RGVwdGgiOjAsInN0b3BPblF1b3RhUmVhY2giOnRydWUsInNwaWtlQXJyZXN0TGltaXQiOjAsInNwaWtlQXJyZXN0VW5pdCI6bnVsbH19LCJrZXl0eXBlIjoiUFJPRFVDVElPTiIsInN1YnNjcmliZWRBUElzIjpbeyJzdWJzY3JpYmVyVGVuYW50RG9tYWluIjoiY2FyYm9uLnN1cGVyIiwibmFtZSI6IkFjY291bnQtRGlyZWN0LUFjY2Vzcy1BUEktU2FuZGJveCIsImNvbnRleHQiOiJcL3NhbmRib3hcL2FkYWFcL3YxIiwicHVibGlzaGVyIjoiYWRtaW4iLCJ2ZXJzaW9uIjoidjEiLCJzdWJzY3JpcHRpb25UaWVyIjoiVW5saW1pdGVkIn1dLCJpYXQiOjE3MDIyODc2NzksImp0aSI6ImRmMmNlY2M0LTNkNDItNDU3Ni1hY2E1LTk5ZDQ1YjVhZDEwYSJ9.fe2yTBFr_jKs1qhVIWzi2Qkfz9K0v3DhzU5vPS94rUMXaKOsdQK2ELjQO1kRuBlR4Y4NX66y5iVMxKEx53mAhSQmsIFaAo72Uhz3u9_FI4ytq8iBa1IU-QWNdL4Y5twmLl3uGK2mMDzItINtaIgAfK47h7r7IhMU1NYIUv_mJesjoqLq93D1QHdYIsfFav7MVU2K9QJSYWyDX0hbNZU28D0_FqbTvXRSAzHyk2uz_fv9xLZB-d5ZgIYOiz8VWvkJ6zTtrWzMEPD7Z4mbdhXrxLoc8IxUCo4N15kYwkEPAQIA0ZW_zN8d_4DPM2kRmMb1moLVcxgxzOCl5KsIYRX4HQ==' \
--header 'Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJLQklEPXRlc3QiLCJhdWRpdFRyYWNraW5nSWQiOiJkNzQxMmZlNS1mZTczLTQ5NDUtYjc5Yy0wYmFmMDEyNzEyNWQiLCJpc3MiOiJodHRwczovL2xvZ2luLmtiLmN6L29wZW5hbS9vYXV0aDIiLCJ0b2tlbk5hbWUiOiJhY2Nlc3NfdG9rZW4iLCJ0b2tlbl90eXBlIjoiQmVhcmVyIiwiYXV0aEdyYW50SWQiOiI2YWNjNzYxZS1hODZlLTRkYjUtODU4YS1kZTBmZmIzNDIzNDEiLCJhdWQiOiIxMjM1NDYiLCJuYmYiOjE3MDIyODgxMDcsInNjb3BlIjpbImFkYWEiXSwicmVhbG0iOiIvIiwiZXhwIjoxNzAyMjkxNzA3LCJpYXQiOjE3MDIyODgxMDcsImV4cGlyZXNfaW4iOjM2MDAwMDAsImp0aSI6IjE2NGNmZWE4LTQ2MGYtNDBjYS1hMTRjLWJlNTZjNmY1YjBjNiJ9.iL-wV62DuWuTYbis48aakFCqZMSD01kNBRt_TLXkWcI'
```

## Response

```js
PDF FILE
```
