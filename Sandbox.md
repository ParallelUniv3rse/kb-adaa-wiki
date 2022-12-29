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
curl --location --request POST 'https://gw.kbcloud.cz/sandbox/oauth2-software-statements/v1/software-statements' \
--header 'x-correlation-id: 1ca9d990-14c0-4a98-b294-80fe8df0c8a5' \
--header 'x-client-cert: valid-certificate' \
--header 'x-api-key: Bearer 87e1330f-cee2-35fb-b290-dcfc2c21bb14' \
--header 'Content-Type: application/json' \
--data-raw '{
  "softwareName": "Nejlepší produkt",
  "softwareNameEn": "Best product",
  "softwareId": "f64bf2e447e545228c78e07b081a82ee",
  "softwareVersion": "1.0",
  "softwareUri": "https://client.example.org",
  "redirectUris": [
    "http://localhost:8888/transactions"
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

> **Check information in JWT token**
> You can check content JWT token on [jwt.io](https://jwt.io)

HTTP 201

>

```
eyJhbGciOiJSUzI1NiJ9.eyJpc3MiOiJLb21lcsSNbsOtIEJhbmthIHMuci5vLiIsImlhdCI6MTU4MDgyNDgxMCwiZXhwIjoxNTk2NTQ5NjEwLCJ2ZW5kb3JOYW1lIjoiQmxvazM3IHMuci5vLiIsInNvZnR3YXJlTmFtZSI6Ik5lamxlcMWhw60gcHJvZHVrdCIsInNvZnR3YXJlTmFtZUVuIjoiQmVzdCBwcm9kdWN0Iiwic29mdHdhcmVJZCI6IjI1YmY0MTFlLWZlZGEtNGE0OS1hYTlmLWRmNjgzNDgwMjY2NCIsInNvZnR3YXJlVmVyc2lvbiI6IjEuMCIsInNvZnR3YXJlVXJpIjoiaHR0cDovL3d3dy5zb2Z0LXdhcmUuY3oiLCJyZWRpcmVjdFVyaXMiOlsiaHR0cDovL2xvY2FsaG9zdDo4ODg4L3RyYW5zYWN0aW9ucyJdLCJ0b2tlbkVuZHBvaW50QXV0aE1ldGhvZCI6ImNsaWVudF9zZWNyZXRfcG9zdCIsImdyYW50VHlwZXMiOlsiYXV0aG9yaXphdGlvbl9jb2RlIl0sInJlc3BvbnNlVHlwZXMiOlsiY29kZSJdLCJyZWdpc3RyYXRpb25CYWNrVXJpIjoiaHR0cDovL3d3dy5zb3RmLXdhcmUuY3ovcmVnaXN0ZXIiLCJjb250YWN0cyI6WyJlbWFpbDogdGVzdEB0ZXN0Lm9yZyJdLCJsb2dvVXJpIjoiaHR0cDovL3d3dy5zb3RmLXdhcmUuY3ovbG9nby5wbmciLCJ0b3NVcmkiOiJodHRwOi8vd3d3LnNvdGYtd2FyZS5jei90b3MiLCJwb2xpY3lVcmkiOiJodHRwOi8vd3d3LnNvdGYtd2FyZS5jei9wb2xpY3kifQ.EMz31yCDaiTNJTI6xQY9d4sHi8aNviuLDXtMdQsl1-dPj3i59UR5d58W8YuWUVPflI79OrXBqFNElqCe6MqPB9I0V89hUrVnOEtsq3XEvPzIaedpVTQ8JOnedmrQi2DEYIXsdo-wuUi9YWRKr-1yfeIOv0NTa_CKjHusS5DH9rb9GoMQro8zEKfaeMBRKh2x1j6kIALhn8_9XpqkAoTnBt9EJ2ek0rKuf4mBXHaLylBUDctqdCuGOg_QPI-oPllR6CKtGkfoAhgBrXQ3zwaXdWwBc24lQ63RARRcvPibtSlaFqfSnQ8bSJ_0_fW3gitlLIyyRj8MPrbZeadsAcnKzA
```

# Application Registration - OAuth2

```json
{
  "clientName": "Nejlepší produkt",
  "clientNameEn": "Best product",
  "applicationType": "web",
  "redirectUris": ["http://localhost:8888/transactions"],
  "scope": ["adaa"],
  "softwareStatement": "eyJhbGciOiJSUzI1NiJ9.eyJpc3MiOiJLb21lcsSNbsOtIEJhbmthIHMuci5vLiIsImlhdCI6MTU4MDgyNDgxMCwiZXhwIjoxNTk2NTQ5NjEwLCJ2ZW5kb3JOYW1lIjoiQmxvazM3IHMuci5vLiIsInNvZnR3YXJlTmFtZSI6Ik5lamxlcMWhw60gcHJvZHVrdCIsInNvZnR3YXJlTmFtZUVuIjoiQmVzdCBwcm9kdWN0Iiwic29mdHdhcmVJZCI6IjI1YmY0MTFlLWZlZGEtNGE0OS1hYTlmLWRmNjgzNDgwMjY2NCIsInNvZnR3YXJlVmVyc2lvbiI6IjEuMCIsInNvZnR3YXJlVXJpIjoiaHR0cDovL3d3dy5zb2Z0LXdhcmUuY3oiLCJyZWRpcmVjdFVyaXMiOlsiaHR0cDovL2xvY2FsaG9zdDo4ODg4L3RyYW5zYWN0aW9ucyJdLCJ0b2tlbkVuZHBvaW50QXV0aE1ldGhvZCI6ImNsaWVudF9zZWNyZXRfcG9zdCIsImdyYW50VHlwZXMiOlsiYXV0aG9yaXphdGlvbl9jb2RlIl0sInJlc3BvbnNlVHlwZXMiOlsiY29kZSJdLCJyZWdpc3RyYXRpb25CYWNrVXJpIjoiaHR0cDovL3d3dy5zb3RmLXdhcmUuY3ovcmVnaXN0ZXIiLCJjb250YWN0cyI6WyJlbWFpbDogdGVzdEB0ZXN0Lm9yZyJdLCJsb2dvVXJpIjoiaHR0cDovL3d3dy5zb3RmLXdhcmUuY3ovbG9nby5wbmciLCJ0b3NVcmkiOiJodHRwOi8vd3d3LnNvdGYtd2FyZS5jei90b3MiLCJwb2xpY3lVcmkiOiJodHRwOi8vd3d3LnNvdGYtd2FyZS5jei9wb2xpY3kifQ.EMz31yCDaiTNJTI6xQY9d4sHi8aNviuLDXtMdQsl1-dPj3i59UR5d58W8YuWUVPflI79OrXBqFNElqCe6MqPB9I0V89hUrVnOEtsq3XEvPzIaedpVTQ8JOnedmrQi2DEYIXsdo-wuUi9YWRKr-1yfeIOv0NTa_CKjHusS5DH9rb9GoMQro8zEKfaeMBRKh2x1j6kIALhn8_9XpqkAoTnBt9EJ2ek0rKuf4mBXHaLylBUDctqdCuGOg_QPI-oPllR6CKtGkfoAhgBrXQ3zwaXdWwBc24lQ63RARRcvPibtSlaFqfSnQ8bSJ_0_fW3gitlLIyyRj8MPrbZeadsAcnKzA",
  "encryptionAlg": "AES-256",
  "encryptionKey": "Ri1KYU5kUmdVa1hwMnM1djh5L0I/RShIK0tiUGVTaFY="
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

ℹ️ This request put in your browser

```
GET
https://openbanking-dev.kb.cz/sandbox/client-api-management/saml/register?registrationRequest=ewoKICAiY2xpZW50TmFtZSI6ICJOZWpsZXDFocOtIHByb2R1a3QiLAogICJjbGllbnROYW1lRW4iOiAiQmVzdCBwcm9kdWN0IiwKICJhcHBsaWNhdGlvblR5cGUiOiAid2ViIiwKICAicmVkaXJlY3RVcmlzIjogWwogICAgImh0dHA6Ly9sb2NhbGhvc3Q6ODg4OC90cmFuc2FjdGlvbnMiCiAgXSwKICAic2NvcGUiOiBbCiAgICAiYWRhYSIKICBdLAogICJzb2Z0d2FyZVN0YXRlbWVudCI6ICJleUpoYkdjaU9pSlNVekkxTmlKOS5leUpwYzNNaU9pSkxiMjFsY3NTTmJzT3RJRUpoYm10aElITXVjaTV2TGlJc0ltbGhkQ0k2TVRVNE1EZ3lORGd4TUN3aVpYaHdJam94TlRrMk5UUTVOakV3TENKMlpXNWtiM0pPWVcxbElqb2lRbXh2YXpNM0lITXVjaTV2TGlJc0luTnZablIzWVhKbFRtRnRaU0k2SWs1bGFteGxjTVdodzYwZ2NISnZaSFZyZENJc0luTnZablIzWVhKbFRtRnRaVVZ1SWpvaVFtVnpkQ0J3Y205a2RXTjBJaXdpYzI5bWRIZGhjbVZKWkNJNklqSTFZbVkwTVRGbExXWmxaR0V0TkdFME9TMWhZVGxtTFdSbU5qZ3pORGd3TWpZMk5DSXNJbk52Wm5SM1lYSmxWbVZ5YzJsdmJpSTZJakV1TUNJc0luTnZablIzWVhKbFZYSnBJam9pYUhSMGNEb3ZMM2QzZHk1emIyWjBMWGRoY21VdVkzb2lMQ0p5WldScGNtVmpkRlZ5YVhNaU9sc2lhSFIwY0RvdkwyeHZZMkZzYUc5emREbzRPRGc0TDNSeVlXNXpZV04wYVc5dWN5SmRMQ0owYjJ0bGJrVnVaSEJ2YVc1MFFYVjBhRTFsZEdodlpDSTZJbU5zYVdWdWRGOXpaV055WlhSZmNHOXpkQ0lzSW1keVlXNTBWSGx3WlhNaU9sc2lZWFYwYUc5eWFYcGhkR2x2Ymw5amIyUmxJbDBzSW5KbGMzQnZibk5sVkhsd1pYTWlPbHNpWTI5a1pTSmRMQ0p5WldkcGMzUnlZWFJwYjI1Q1lXTnJWWEpwSWpvaWFIUjBjRG92TDNkM2R5NXpiM1JtTFhkaGNtVXVZM292Y21WbmFYTjBaWElpTENKamIyNTBZV04wY3lJNld5SmxiV0ZwYkRvZ2RHVnpkRUIwWlhOMExtOXlaeUpkTENKc2IyZHZWWEpwSWpvaWFIUjBjRG92TDNkM2R5NXpiM1JtTFhkaGNtVXVZM292Ykc5bmJ5NXdibWNpTENKMGIzTlZjbWtpT2lKb2RIUndPaTh2ZDNkM0xuTnZkR1l0ZDJGeVpTNWplaTkwYjNNaUxDSndiMnhwWTNsVmNta2lPaUpvZEhSd09pOHZkM2QzTG5OdmRHWXRkMkZ5WlM1amVpOXdiMnhwWTNraWZRLkVNejMxeUNEYWlUTkpUSTZ4UVk5ZDRzSGk4YU52aXVMRFh0TWRRc2wxLWRQajNpNTlVUjVkNThXOFl1V1VWUGZsSTc5T3JYQnFGTkVscUNlNk1xUEI5STBWODloVXJWbk9FdHNxM1hFdlB6SWFlZHBWVFE4Sk9uZWRtclFpMkRFWUlYc2RvLXd1VWk5WVdSS3ItMXlmZUlPdjBOVGFfQ0tqSHVzUzVESDlyYjlHb01Rcm84ekVLZmFlTUJSS2gyeDFqNmtJQUxobjhfOVhwcWtBb1RuQnQ5RUoyZWswckt1ZjRtQlhIYUx5bEJVRGN0cWRDdUdPZ19RUEktb1BsbFI2Q0t0R2tmb0FoZ0JyWFEzendhWGRXd0JjMjRsUTYzUkFSUmN2UGlidFNsYUZxZlNuUThiU0pfMF9mVzNnaXRsTEl5eVJqOE1QcmJaZWFkc0Fjbkt6QSIsCiAgImVuY3J5cHRpb25BbGciOiAiQUVTLTI1NiIsCiAgImVuY3J5cHRpb25LZXkiOiAiUmkxS1lVNWtVbWRWYTFod01uTTFkamg1TDBJL1JTaElLMHRpVUdWVGFGWT0iCn0=&state=client123
```

> Identification request
>
> Use parameter "state", the parameter state get back with response

## Response

```
HTTP 302 Found
http://localhost:8888/transactions?salt=rrU94Nc3Z6gPBQV3&encryptedData=WR-euAw6XHge5iEPKjE66YTOOSuHir57kkI3Fb6FCE3OVIPBz9Kdcck5li6xaAUJQdy7Ih90v_LuHn7nHiGhHvgsh3Dj8wYKsmFS2PG4x73UD7843SIc5apwUhHEE_uR9iS9EB3CvwPty4y4YyniTTlJ5WSlyYg2DqXVbo3fi3lXArQG-pptuaMdbFj3uftXTdvdpWJZ5JJBNXizGg48YQYgUerajl9gx717Aki1ZsvNGw_IYC8oEMEFEfk-Rn2UToJ5pmuPgpdwGcCaF5z7_kxyknDVsr2p6ue4ypTqJheGdMIcXKQ-Vs2iq55AWR61k8TttvruPq4LfTbPk60xZX0xuveJG9kHvLu7k5WKDXcS-VX_SwFXYHrxFaa0DDOONT8rSmozQso_gB5rtR4Jlb2dbhvUg7pUG2nZMs8BSmOX_ry2dug7t8XYxxE9pdfTZb4KWzLzOh-MeDB-NcWRSg8fG4AXZV41sDLXlGVbGms5nwxOky5phvr8i2Ks-vx75OCBC6MCpL0d1sHI-8CSX-PEd7NzMiIbLuAWU0hAf461HlIqGJNdr9oFovpq7EZxy1bJyLXFhYTVP8rWjQZYixckEHhY7ElSiziJjLd3to8EqiAvWuzv2qEdzn_cmKYXWIWVT4L2AAswhmtHw_2G0tGvW-YXv5K_-ZMl8WGSECaw4v6CbyA8VerEiL0GOAaZSfdxzNez3mvsljs0rmH0KBU-pQWbY6MnNdxfXOuK_PeLQ01taU-1UVyr3t41aRNmBPk6pAlqFXGu3Z_rlvJjwGs6OT1OHQTi6OAeMVUQN5oPhCPHNZdkQ3LsxnMzaQ7WXqxNY2riC150ad0Wy1od1gKZuVToMLPAY6hu0fDxseZvKn64bGbRZ2ZUrd-cZ_ihDKm6pADwfg0Nv69O5SctWMYBeakihAIvIWb8083aySxhRlJ8tdPsgy3RB3PvpULA--JWmBiXtIBtHmg80TdMYYwxPOa319xblONIqAOSGnMW7QMlwfbmROsCNP9mSfgINkZKzRUWVyaJnPOJmAMMHya3AxGsK9ZD5zjZFaFcMThyWlTGCnOY5c5FtgBiuYbbiIBp0O9JDBIlI3NS4Q71e3uv3Wc6ipUZSzkaeGBXMt-yOS_56Gd3yrz7_Vgf5yHyVgGAKAyWnD7cIFvShts_bbT3oZzoS_ZxWSSucreTfjpQ0TXM7kXn&state=client123
```

## Decrypt response

<details><summary>example Java</summary>

[Source code on Github](https://github.com/komercka/adaa-example-spring-boot/blob/b24d79543d987d71183620e48806fcb48722d52c/core/src/main/java/cz/kb/openbanking/adaa/example/springboot/core/decryption/impl/Aes256DecryptionServiceImpl.java#L29)

</details>

<details><summary>example PHP</summary>

```php
<?php
// JSON property encryptionKey of registrationRequest, base64 encoded
$key = $encryptionKey = "MnM1djh5L0I/RShIK01iUWVUaFdtWnEzdDZ3OXokQyY=";
// GET parameter salt, base64url encoded
$initialization_vector = $salt = "u1W5ABqw9YEcTLgq";
// GET parameter encryptedData, base64url encoded
$ciphertext = $encryptedData = "h_tAxLwOi41acN4aYy5DOCRnO5bEgENYW_KtwhLPQqZekRbRUoy7jpOShel03we4vovUtfUBCA3VgKyO1lNUFD68844JmGwIEJAp_M2hGhg1qdKbrvuM3CBObxb64ohqcCdyeNuUNRhCnIk5STEI3sju05WoOzImtucH6ftIbf3uVxKoyCQEbadFbEulyGLEqe4sCXkYBMHVShGRWkKBKKuVrc0RWTVcUZqszOOdz1ozBBxHaBrER_eOuJa3uDkvBhGSnpJWf_GD0G9qUH46zjXEo6ZbQUVgrA3OZLAlaOjazpRsKkDPMqIU3JTyB8sVb6pT1gryLo6SbvG9cQhten70X_v3cY75s8-6KBMwi7e9Y28-rC264DQyNKUh30zh2nqs-SzQUL9-QWIttXx4mRNNydhnDOCEb8Hij0fWZogLK_CcmOVx6jtoSuac9LCqN_Wr5rA1uKfDrhDB60AvWY7bFIbKOA3n6jYefsPkSFCXJ2teP3UyODAofWrlWZMMDY1X7qQ3QtJ5qeCRxR4WFIdhW8RdWLE6scY9AUVAmh8zCKb7xrstX7WcgBXW1_xSQkOpWdvl3wLoi9-bMMj4sWp04iP_pET4Md6n-rTGxEJ3WN4z6Y4ebDc0C7CZqq2YbPXmJeKJg5C2xbIcIOgTCqtkYXXQltl0XdX-HpUujjrf5WLEguOenARWCqBqNPWKK37f-vnic8qxMbMWOXdGnClEtv5wpHd_UzVmQ3ynNsyHUz1mldN3WiwZycZRjEGgpq7TvmKWEmTuNBmubPeGR2QyF0nmKzSuIXtC5ID4EFGDQCfYtMPUvVaekUlKvi_X7anSaQgkXr13EDJ2XxpDRdeZ79KuNil0ySo2icIvkADpgGhdileyOhXbV9g553HnUWFm0hQ5IUlYMKwn05WuO-4wFyl63iQ76nO1w2kWJTEIxh0EiTPF6dugCtZq7ct_OHhpAug2GJzlAHqShVuvgUIDyj2H-Igh1d87EqSOVlP1--z30ikGgiueAIAkjAb3";

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
  "redirect_uris": "https://client.example.org/callback-backup, https://client.example.org/callback",
  "client_name": "Nejlepší produkt",
  "client_name#en-US": "Best product",
  "logo_uri": "https: client.example.org/logo.png",
  "policy_uri": "https://client.example.org/policy",
  "tos_uri": "https://client.example.org/tos",
  "contact": "example@goodsoft.com",
  "contacts": ["example@goodsoft.com"],
  "scopes": ["adaa"],
  "scope": "adaa",
  "response_types": ["code"],
  "response_type": "code",
  "grant_types": ["refresh_token", "authorization_code"],
  "subject_type": "public",
  "token_endpoint_auth_method": "client_secret_post",
  "require_auth_time": false,
  "bin": "29145643",
  "client_id": "Nejlepsiprodukt-6073",
  "client_secret": "aIiAgTXYH6v9C_5ckhiKNA",
  "api_key": "NOT_PROVIDED",
  "registration_client_uri": "https://uat2-caas.kb.cz/openam/json/caas/api/oauth2/register/Nejlepsiprodukt-6073",
  "client_id_issued_at": 1632908786
}
```

# Authorization code

> Token validity
> Code has validity only 2 minutes

## Requests

```
GET
https://kb-openbanking-oauth2.azurewebsites.net/?response_type=code&client_id=Nejlepsiprodukt-6073&redirect_uri=REDIRECT_URI&scope=adaa&state=xyz
```

## Response

```
HTTP 302 Found
https://client.example.org/callback?code=-_N2RrJRCMgd__JGqUlB_KaFNpo&iss=https%3A%2F%2Fcaas.kb.cz%2Fopenam%2Foauth2&client_id=Nejlepsiprodukt-4176
```

# Refresh token

> Token validity
> refresh_token validity 12 months

## Request

```
curl --location --request POST 'https://gw.kbcloud.cz/sandbox/oauth2/v1/access_token' \
--header 'x-correlation-id: 75f2af05-17ce-467a-96b1-fdb86c07533c' \
--header 'x-api-key: Bearer 87e1330f-cee2-35fb-b290-dcfc2c21bb14' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode 'grant_type=authorization_code' \
--data-urlencode 'redirect_uri=www.kb.cz' \
--data-urlencode 'code=eyJ1c2VySWQiOiJ0ZXN0Iiwic2NvcGVzIjpbImFkYWEiXX0' \
--data-urlencode 'client_id=client1' \
--data-urlencode 'client_secret=password'
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

```
curl --location --request POST 'https://gw.kbcloud.cz/sandbox/oauth2/v1/access_token' \
--header 'x-correlation-id: 75f2af05-17ce-467a-96b1-fdb86c07533c' \
--header 'x-api-key: Bearer 87e1330f-cee2-35fb-b290-dcfc2c21bb14' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode 'grant_type=authorization_code' \
--data-urlencode 'redirect_uri=www.kb.cz' \
--data-urlencode 'code=eyJ1c2VySWQiOiJ0ZXN0Iiwic2NvcGVzIjpbImFkYWEiXX0' \
--data-urlencode 'client_id=client1' \
--data-urlencode 'client_secret=password'
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

```
curl --location --request GET 'https://gw.kbcloud.cz/sandbox/adaa/v1/accounts/' \
--header 'x-correlation-id: 3d9d62ff-17cb-4107-bf5a-f9ce8d0dff9a' \
--header 'x-api-key: Bearer 87e1330f-cee2-35fb-b290-dcfc2c21bb14' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJLQklEPXRlc3QiLCJhdWRpdFRyYWNraW5nSWQiOiJkNzQxMmZlNS1mZTczLTQ5NDUtYjc5Yy0wYmFmMDEyNzEyNWQiLCJpc3MiOiJodHRwczovL2xvZ2luLmtiLmN6L29wZW5hbS9vYXV0aDIiLCJ0b2tlbk5hbWUiOiJhY2Nlc3NfdG9rZW4iLCJ0b2tlbl90eXBlIjoiQmVhcmVyIiwiYXV0aEdyYW50SWQiOiI2YWNjNzYxZS1hODZlLTRkYjUtODU4YS1kZTBmZmIzNDIzNDEiLCJhdWQiOiIxMjM1NDYiLCJuYmYiOjE2Njg0Mjg0OTksInNjb3BlIjpbImFkYWEiXSwicmVhbG0iOiIvIiwiZXhwIjoxNjY4NDMyMDk5LCJpYXQiOjE2Njg0Mjg0OTksImV4cGlyZXNfaW4iOjM2MDAwMDAsImp0aSI6IjE2NGNmZWE4LTQ2MGYtNDBjYS1hMTRjLWJlNTZjNmY1YjBjNiJ9.-MYDD540bx4rCgFPVVd9FruDHuCrwkDmv5OqbDW7vjQ' \
--data-raw ''
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

```
curl --location --request GET 'https://gw.kbcloud.cz/sandbox/adaa/v1/accounts/Q1oxMzAxMDAwOTAxMTQ3NzcxODAwMjI3OkNaSw/transactions?fromDate=2019-01-10&toDate=2019-10-10&page=0&size=20' \
--header 'x-correlation-id: 1201cf3f-2fef-4515-b54c-bd2776253535' \
--header 'x-api-key: Bearer 87e1330f-cee2-35fb-b290-dcfc2c21bb14' \
--header 'Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJLQklEPXRlc3QiLCJhdWRpdFRyYWNraW5nSWQiOiJkNzQxMmZlNS1mZTczLTQ5NDUtYjc5Yy0wYmFmMDEyNzEyNWQiLCJpc3MiOiJodHRwczovL2xvZ2luLmtiLmN6L29wZW5hbS9vYXV0aDIiLCJ0b2tlbk5hbWUiOiJhY2Nlc3NfdG9rZW4iLCJ0b2tlbl90eXBlIjoiQmVhcmVyIiwiYXV0aEdyYW50SWQiOiI2YWNjNzYxZS1hODZlLTRkYjUtODU4YS1kZTBmZmIzNDIzNDEiLCJhdWQiOiIxMjM1NDYiLCJuYmYiOjE2Njg0Mjg0OTksInNjb3BlIjpbImFkYWEiXSwicmVhbG0iOiIvIiwiZXhwIjoxNjY4NDMyMDk5LCJpYXQiOjE2Njg0Mjg0OTksImV4cGlyZXNfaW4iOjM2MDAwMDAsImp0aSI6IjE2NGNmZWE4LTQ2MGYtNDBjYS1hMTRjLWJlNTZjNmY1YjBjNiJ9.-MYDD540bx4rCgFPVVd9FruDHuCrwkDmv5OqbDW7vjQ'
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

# Statements - List of statements

## Request

```js
curl --location --request GET 'https://api.kb.cz/open/api/adaa/v1/accounts/eXBCcDBLUEFCT0Y0MUFSS2x6b0RNZUJHZzJHdk5wSlhFWWdKeWEySFlabkU4OEZJQTcxU05kLzc1SnFKa0dlZmF2RzRQbHgrVDY1QXZvZHhNWXZ1Vnc9PQ/statements?dateFrom=2021-03-30T15:42:30.000Z' \
--header 'x-correlation-id: 6491e392-e4ef-46a3-bd68-6b0696ab6cf3' \
--header 'x-api-key: Bearer 3a7f779a-8cc1-364f-be2b-9ea161f63817' \
--header 'Authorization: Bearer eyJ0eXAiOiJKV1QiLCJraWQiOiJ3RjJTa1I3NWMxamZsZ1VIOWJ6Wno3Tzllemc9IiwiYWxnIjoiUlMyNTYifQ.eyJzdWIiOiJBUElJRD01MmYwNDgyNjM3OTM0ZGZmOWY5MjE1MTBhMjlhMWYwYSIsImN0cyI6Ik9BVVRIMl9TVEFURUxFU1NfR1JBTlQiLCJhdXRoX2xldmVsIjo2LCJhdWRpdFRyYWNraW5nSWQiOiJhYmY1ZjE3Yi0wYjEwLTRjYjAtYWJkMi1iN2U4OGFhYTM4ZDgtNTcwMjgyNDkiLCJpc3MiOiJodHRwczovL2NhYXMua2IuY3ovb3BlbmFtL29hdXRoMiIsInRva2VuTmFtZSI6ImFjY2Vzc190b2tlbiIsInRva2VuX3R5cGUiOiJCZWFyZXIiLCJhdXRoR3JhbnRJZCI6IjF1bzJ1ZHNjS0dLSWQwVjFFT2ZzRW1sUUtQcyIsImF1ZCI6IktpZmxpLTE2MzUiLCJuYmYiOjE2NTU5NzE2NjksImdyYW50X3R5cGUiOiJyZWZyZXNoX3Rva2VuIiwic2NvcGUiOlsiYWRhYSJdLCJhdXRoX3RpbWUiOjE2NTUzNzcyNzMsInJlYWxtIjoiLyIsImV4cCI6MTY1NTk3MTg0OSwiaWF0IjoxNjU1OTcxNjY5LCJleHBpcmVzX2luIjoxODAsImp0aSI6IlhDOWdKcVJBVVBOdDVSbFZqUjVZME1UdlQyWSIsImNhYXNPcGVyYXRpb25JZCI6IjUyNzYyMTc3NmRiODQ0MTg5MGJjM2MzM2RkZjYzYmVlIn0.cLirxtAxy7bOao5sdXUBR118cHvasHoe_YMlWs51iR7Y-T4bwX6XbKWVlqeIqe62J4r17ZCsDvagScLjabGDji8zwkJvX8are9d3RouepVaza54whBtg6QS7ItE7IGiqlQCfod4Pz39Fa_0dmdI_nfrU_VST4l99jL4chFD5v0JOZ5tFBYiRcXl6Rc_msYX5DvGb40_PNPQVQgUlMm1j97qiSXfs_NTsk7o8uGw_bE6V1OlnpDDu3JjTgi2wbaOp6KPPYWIc9o2rdmUr4nMzaaU5JVEZkn4gD8Dojbcr9PhLyUaH7ACWWKguolK3WjFQj6ROI2nJ0tEF-hphnS8reA'
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

```js
curl --location --request GET 'https://api.kb.cz/open/api/adaa/v1/accounts/eXBCcDBLUEFCT0Y0MUFSS2x6b0RNZUJHZzJHdk5wSlhFWWdKeWEySFlabkU4OEZJQTcxU05kLzc1SnFKa0dlZmF2RzRQbHgrVDY1QXZvZHhNWXZ1Vnc9PQ/statements/325723851' \
--header 'x-correlation-id: becb6607-dcf1-4209-b125-0f12e9a68bd6' \
--header 'x-api-key: Bearer 3a7f779a-8cc1-364f-be2b-9ea161f63817' \
--header 'Authorization: Bearer eyJ0eXAiOiJKV1QiLCJraWQiOiJ3RjJTa1I3NWMxamZsZ1VIOWJ6Wno3Tzllemc9IiwiYWxnIjoiUlMyNTYifQ.eyJzdWIiOiJBUElJRD01MmYwNDgyNjM3OTM0ZGZmOWY5MjE1MTBhMjlhMWYwYSIsImN0cyI6Ik9BVVRIMl9TVEFURUxFU1NfR1JBTlQiLCJhdXRoX2xldmVsIjo2LCJhdWRpdFRyYWNraW5nSWQiOiJhYmY1ZjE3Yi0wYjEwLTRjYjAtYWJkMi1iN2U4OGFhYTM4ZDgtNDI1MzExODkiLCJpc3MiOiJodHRwczovL2NhYXMua2IuY3ovb3BlbmFtL29hdXRoMiIsInRva2VuTmFtZSI6ImFjY2Vzc190b2tlbiIsInRva2VuX3R5cGUiOiJCZWFyZXIiLCJhdXRoR3JhbnRJZCI6IjF1bzJ1ZHNjS0dLSWQwVjFFT2ZzRW1sUUtQcyIsImF1ZCI6IktpZmxpLTE2MzUiLCJuYmYiOjE2NTU3MjIzNjAsImdyYW50X3R5cGUiOiJyZWZyZXNoX3Rva2VuIiwic2NvcGUiOlsiYWRhYSJdLCJhdXRoX3RpbWUiOjE2NTUzNzcyNzMsInJlYWxtIjoiLyIsImV4cCI6MTY1NTcyMjU0MCwiaWF0IjoxNjU1NzIyMzYwLCJleHBpcmVzX2luIjoxODAsImp0aSI6Ijl3emVDSUgwRXJ0TmF4UHJJdDVXSjdUTW51WSIsImNhYXNPcGVyYXRpb25JZCI6IjUyNzYyMTc3NmRiODQ0MTg5MGJjM2MzM2RkZjYzYmVlIn0.oeRegYbg656c_95OVNm9oUBjx9xIQV5Xuo9QJ4nQUaDNy4Zczr9rHjfsPx0Hevn1rITOcsCaPyQHBzkV3WGLzqJ_Pna3eqxF5Wga36BNQlYDGzgVF5X0tg5-7swUcH2WsOSuPR-qDtyGNODe3ZDk2WBrmZBmXJwaivvxlM14yNzP2KFi4Jp5zi2CrgfYUGUc-p2qvegNJFLEvqPP9RR0W_5lGdRJ9LoVpYDEHfOB7oZ4GPwBPoQuXxplmvVNoWP6khitGAKLCj8Rx-ikeiaJHZjhXV42rjE6UCMxkh1qRHBeRv9x6zPKo5WYrKlr542a0Itr0OYPc2LeOnr7F274Rg'
```

## Response

```js
PDF FILE
```
