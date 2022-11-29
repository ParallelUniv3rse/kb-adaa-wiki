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

> **Check information in JWT token**
> You can check content JWT token on [jwt.io](https://jwt.io)

HTTP 201

>

```
eyJhbGciOiJIUzI1NiJ9.eyJ2ZW5kb3JOYW1lIjoiQ29tcGFueSBhLnMuIiwic29mdHdhcmVOYW1lIjoiTmVqbGVwxaHDrSBwcm9kdWt0Iiwic29mdHdhcmVOYW1lRW4iOiJCZXN0IHByb2R1Y3QiLCJzb2Z0d2FyZUlkIjoiZjY0YmYyZTQ0N2U1NDUyMjhjNzhlMDdiMDgxYTgyZWUiLCJzb2Z0d2FyZVZlcnNpb24iOiIxLjAiLCJzb2Z0d2FyZVVyaSI6Imh0dHBzOi8vY2xpZW50LmV4YW1wbGUub3JnIiwicmVkaXJlY3RVcmlzIjpbImh0dHBzOi8vY2xpZW50LmV4YW1wbGUub3JnL2NhbGxiYWNrIiwiaHR0cHM6Ly9jbGllbnQuZXhhbXBsZS5vcmcvY2FsbGJhY2stYmFja3VwIl0sInRva2VuRW5kcG9pbnRBdXRoTWV0aG9kIjoiY2xpZW50X3NlY3JldF9wb3N0IiwiZ3JhbnRUeXBlcyI6WyJhdXRob3JpemF0aW9uX2NvZGUiXSwicmVzcG9uc2VUeXBlcyI6WyJjb2RlIl0sInJlZ2lzdHJhdGlvbkJhY2tVcmkiOiJodHRwczovL2NsaWVudC5leGFtcGxlLm9yZy9iYWNrdXJpIiwiY29udGFjdHMiOlsiZW1haWw6IGV4YW1wbGVAZ29vZHNvZnQuY29tIl0sImxvZ29VcmkiOiJodHRwczovL2NsaWVudC5leGFtcGxlLm9yZy9sb2dvLnBuZyIsInRvc1VyaSI6Imh0dHBzOi8vY2xpZW50LmV4YW1wbGUub3JnL3RvcyIsInBvbGljeVVyaSI6Imh0dHBzOi8vY2xpZW50LmV4YW1wbGUub3JnL3BvbGljeSJ9.Fw11ePNty7aimkm3yBYMoK5L-8Blpec4CafNJ-giC4g
```

# Application Registration - OAuth2

```json
{
  "clientName": "Nejlepší produkt",
  "clientNameEn": "Best product",
  "applicationType": "web",
  "redirectUris": ["https://client.example.org/callback"],
  "scope": ["adaa", "bpisp", "card_data"],
  "encryptionKey": "MnM1djh5L0I/RShIK01iUWVUaFdtWnEzdDZ3OXokQyY=“,
  "encryptionAlg": "AES-256",
  "softwareStatement": "eyJhbGciOiJIUzI1NiJ9.eyJ2ZW5kb3JOYW1lIjoiQ29tcGFueSBhLnMuIiwic29mdHdhcmVOYW1lIjoiTmVqbGVwxaHDrSBwcm9kdWt0Iiwic29mdHdhcmVOYW1lRW4iOiJCZXN0IHByb2R1Y3QiLCJzb2Z0d2FyZUlkIjoiZjY0YmYyZTQ0N2U1NDUyMjhjNzhlMDdiMDgxYTgyZWUiLCJzb2Z0d2FyZVZlcnNpb24iOiIxLjAiLCJzb2Z0d2FyZVVyaSI6Imh0dHBzOi8vY2xpZW50LmV4YW1wbGUub3JnIiwicmVkaXJlY3RVcmlzIjpbImh0dHBzOi8vY2xpZW50LmV4YW1wbGUub3JnL2NhbGxiYWNrIiwiaHR0cHM6Ly9jbGllbnQuZXhhbXBsZS5vcmcvY2FsbGJhY2stYmFja3VwIl0sInRva2VuRW5kcG9pbnRBdXRoTWV0aG9kIjoiY2xpZW50X3NlY3JldF9wb3N0IiwiZ3JhbnRUeXBlcyI6WyJhdXRob3JpemF0aW9uX2NvZGUiXSwicmVzcG9uc2VUeXBlcyI6WyJjb2RlIl0sInJlZ2lzdHJhdGlvbkJhY2tVcmkiOiJodHRwczovL2NsaWVudC5leGFtcGxlLm9yZy9iYWNrdXJpIiwiY29udGFjdHMiOlsiZW1haWw6IGV4YW1wbGVAZ29vZHNvZnQuY29tIl0sImxvZ29VcmkiOiJodHRwczovL2NsaWVudC5leGFtcGxlLm9yZy9sb2dvLnBuZyIsInRvc1VyaSI6Imh0dHBzOi8vY2xpZW50LmV4YW1wbGUub3JnL3RvcyIsInBvbGljeVVyaSI6Imh0dHBzOi8vY2xpZW50LmV4YW1wbGUub3JnL3BvbGljeSJ9.Fw11ePNty7aimkm3yBYMoK5L-8Blpec4CafNJ-giC4g"
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
ewogICJjbGllbnROYW1lIjogIk5lamxlcMWhw60gcHJvZHVrdCIsCiAgImNsaWVudE5hbWVFbiI6ICJCZXN0IHByb2R1Y3QiLAogICJhcHBsaWNhdGlvblR5cGUiOiAid2ViIiwKICAicmVkaXJlY3RVcmlzIjogWyJodHRwczovL2NsaWVudC5leGFtcGxlLm9yZy9jYWxsYmFjayJdLAogICJzY29wZSI6IFsiYWRhYSIsICJicGlzcCIsICJjYXJkX2RhdGEiXSwKICAiZW5jcnlwdGlvbktleSI6ICJNbk0xZGpoNUwwSS9SU2hJSzAxaVVXVlVhRmR0V25FemREWjNPWG9rUXlZPeKAnCwKICAiZW5jcnlwdGlvbkFsZyI6ICJBRVMtMjU2IiwKICAic29mdHdhcmVTdGF0ZW1lbnQiOiAiZXlKaGJHY2lPaUpJVXpJMU5pSjkuZXlKMlpXNWtiM0pPWVcxbElqb2lRMjl0Y0dGdWVTQmhMbk11SWl3aWMyOW1kSGRoY21WT1lXMWxJam9pVG1WcWJHVnd4YUhEclNCd2NtOWtkV3QwSWl3aWMyOW1kSGRoY21WT1lXMWxSVzRpT2lKQ1pYTjBJSEJ5YjJSMVkzUWlMQ0p6YjJaMGQyRnlaVWxrSWpvaVpqWTBZbVl5WlRRME4yVTFORFV5TWpoak56aGxNRGRpTURneFlUZ3laV1VpTENKemIyWjBkMkZ5WlZabGNuTnBiMjRpT2lJeExqQWlMQ0p6YjJaMGQyRnlaVlZ5YVNJNkltaDBkSEJ6T2k4dlkyeHBaVzUwTG1WNFlXMXdiR1V1YjNKbklpd2ljbVZrYVhKbFkzUlZjbWx6SWpwYkltaDBkSEJ6T2k4dlkyeHBaVzUwTG1WNFlXMXdiR1V1YjNKbkwyTmhiR3hpWVdOcklpd2lhSFIwY0hNNkx5OWpiR2xsYm5RdVpYaGhiWEJzWlM1dmNtY3ZZMkZzYkdKaFkyc3RZbUZqYTNWd0lsMHNJblJ2YTJWdVJXNWtjRzlwYm5SQmRYUm9UV1YwYUc5a0lqb2lZMnhwWlc1MFgzTmxZM0psZEY5d2IzTjBJaXdpWjNKaGJuUlVlWEJsY3lJNld5SmhkWFJvYjNKcGVtRjBhVzl1WDJOdlpHVWlYU3dpY21WemNHOXVjMlZVZVhCbGN5STZXeUpqYjJSbElsMHNJbkpsWjJsemRISmhkR2x2YmtKaFkydFZjbWtpT2lKb2RIUndjem92TDJOc2FXVnVkQzVsZUdGdGNHeGxMbTl5Wnk5aVlXTnJkWEpwSWl3aVkyOXVkR0ZqZEhNaU9sc2laVzFoYVd3NklHVjRZVzF3YkdWQVoyOXZaSE52Wm5RdVkyOXRJbDBzSW14dloyOVZjbWtpT2lKb2RIUndjem92TDJOc2FXVnVkQzVsZUdGdGNHeGxMbTl5Wnk5c2IyZHZMbkJ1WnlJc0luUnZjMVZ5YVNJNkltaDBkSEJ6T2k4dlkyeHBaVzUwTG1WNFlXMXdiR1V1YjNKbkwzUnZjeUlzSW5CdmJHbGplVlZ5YVNJNkltaDBkSEJ6T2k4dlkyeHBaVzUwTG1WNFlXMXdiR1V1YjNKbkwzQnZiR2xqZVNKOS5GdzExZVBOdHk3YWlta20zeUJZTW9LNUwtOEJscGVjNENhZk5KLWdpQzRnIgp9
```

## Request

ℹ️ This request put in your browser

```
GET
https://kb-openbanking-client-api-management.azurewebsites.net/saml/register?registrationRequest=ewogICJjbGllbnROYW1lIjogIk5lamxlcMWhw60gcHJvZHVrdCIsCiAgImNsaWVudE5hbWVFbiI6ICJCZXN0IHByb2R1Y3QiLAogICJhcHBsaWNhdGlvblR5cGUiOiAid2ViIiwKICAicmVkaXJlY3RVcmlzIjogWyJodHRwczovL2NsaWVudC5leGFtcGxlLm9yZy9jYWxsYmFjayJdLAogICJzY29wZSI6IFsiYWRhYSIsICJicGlzcCIsICJjYXJkX2RhdGEiXSwKICAiZW5jcnlwdGlvbktleSI6ICJNbk0xZGpoNUwwSS9SU2hJSzAxaVVXVlVhRmR0V25FemREWjNPWG9rUXlZPeKAnCwKICAiZW5jcnlwdGlvbkFsZyI6ICJBRVMtMjU2IiwKICAic29mdHdhcmVTdGF0ZW1lbnQiOiAiZXlKaGJHY2lPaUpJVXpJMU5pSjkuZXlKMlpXNWtiM0pPWVcxbElqb2lRMjl0Y0dGdWVTQmhMbk11SWl3aWMyOW1kSGRoY21WT1lXMWxJam9pVG1WcWJHVnd4YUhEclNCd2NtOWtkV3QwSWl3aWMyOW1kSGRoY21WT1lXMWxSVzRpT2lKQ1pYTjBJSEJ5YjJSMVkzUWlMQ0p6YjJaMGQyRnlaVWxrSWpvaVpqWTBZbVl5WlRRME4yVTFORFV5TWpoak56aGxNRGRpTURneFlUZ3laV1VpTENKemIyWjBkMkZ5WlZabGNuTnBiMjRpT2lJeExqQWlMQ0p6YjJaMGQyRnlaVlZ5YVNJNkltaDBkSEJ6T2k4dlkyeHBaVzUwTG1WNFlXMXdiR1V1YjNKbklpd2ljbVZrYVhKbFkzUlZjbWx6SWpwYkltaDBkSEJ6T2k4dlkyeHBaVzUwTG1WNFlXMXdiR1V1YjNKbkwyTmhiR3hpWVdOcklpd2lhSFIwY0hNNkx5OWpiR2xsYm5RdVpYaGhiWEJzWlM1dmNtY3ZZMkZzYkdKaFkyc3RZbUZqYTNWd0lsMHNJblJ2YTJWdVJXNWtjRzlwYm5SQmRYUm9UV1YwYUc5a0lqb2lZMnhwWlc1MFgzTmxZM0psZEY5d2IzTjBJaXdpWjNKaGJuUlVlWEJsY3lJNld5SmhkWFJvYjNKcGVtRjBhVzl1WDJOdlpHVWlYU3dpY21WemNHOXVjMlZVZVhCbGN5STZXeUpqYjJSbElsMHNJbkpsWjJsemRISmhkR2x2YmtKaFkydFZjbWtpT2lKb2RIUndjem92TDJOc2FXVnVkQzVsZUdGdGNHeGxMbTl5Wnk5aVlXTnJkWEpwSWl3aVkyOXVkR0ZqZEhNaU9sc2laVzFoYVd3NklHVjRZVzF3YkdWQVoyOXZaSE52Wm5RdVkyOXRJbDBzSW14dloyOVZjbWtpT2lKb2RIUndjem92TDJOc2FXVnVkQzVsZUdGdGNHeGxMbTl5Wnk5c2IyZHZMbkJ1WnlJc0luUnZjMVZ5YVNJNkltaDBkSEJ6T2k4dlkyeHBaVzUwTG1WNFlXMXdiR1V1YjNKbkwzUnZjeUlzSW5CdmJHbGplVlZ5YVNJNkltaDBkSEJ6T2k4dlkyeHBaVzUwTG1WNFlXMXdiR1V1YjNKbkwzQnZiR2xqZVNKOS5GdzExZVBOdHk3YWlta20zeUJZTW9LNUwtOEJscGVjNENhZk5KLWdpQzRnIgp9&state=client123
```

> Identification request
>
> Use parameter "state", the parameter state get back with response

## Response

```
HTTP 302 Found
https://client.example.org/backuri?salt=1gwqD9tGLtaWRRwU&encryptedData=m5XPrBzLdlEf8OvboBz7ca8OIjmxylEWqG71mcd4GLGKpkTBxVjuJUQRITqYoY4CTC5zb99rUu_26W3uY8nS_w_-nFaYYg0upWj0bU4ftTKwmgHIyXWGw4O4BkcRayzYkgPD71Q9MGBcKnuDHJBeo3mMAI08FVmCa7FHTxRzRaes0Te7VPJlMX_mRBKGmMeXVFU4FdQqdzDu6CfA7IehEgOyjv5-zweRavBFlHp9GJ7lqbIF771Q0prCseokcpNm_2AWav-WBdA7PUzI4TXMBRFUkBmp6eYnIE24PasQ5loW28YWjRF6wigOx6S3S_sDDm0pKjWYtco_vObGn0xRlUjK139RJObQ4cCaiELRQ1uKTObn2sqRi1gAIB3ZB8sJkeEz-vmJDPqovuXc0VgQ_TG-MBRnKuo-utm6z4quI4kUsdggrWNRyPB86lryFZJFh-Ay3P9IuyXOpafHZMndl6W9Jrv9XTpGQFs5hcpY2NHUocqE-4U54ev0F1Ag4WO18Xeek8LQmWOcrzwbFDQs6RkOqO80cMTSA3DklPqHaJChSzGLj4-51yBLkPfwUu-MyT-I9BfsVVXtKB3oSuLZ_jaJpN1-fK0770HftDcR1YNCkN4KvoDUgThL59Gc2uHh-_NtNXse3xRz9rhs2qydJjHIhWPSiY6AMQPzF04frW7XygOeAxYv5475BGX5DD5GN59ZvmhNLbw27P5rNOh3dPF92WQKpTCEv68_qJCXrOzqUL5EiuEKVoQ7SUsrYbKDE76crkEuOihAdI6forHVWd7ixLPYga_ufrMrHau3pT7_5z7h9lEThrn1nnL72Lgh_UaXxE5e6KwNOiLu4JdfzZdufjLWaP7aF5tpE-5OgYuEdA4__yZHeum-Hkmj8WxLNyxixgZoflPqV-RlX_nFQ3D3cN2_k0G7AnEYo7N2PbyqavWSFGnXbI0g6NS_YU-eeQ4YHy38sAP9z1k8TDPxoHR-zki7JFperSraEk2_zTmUKLZCZ_xXIAQi24Y6SKt9q1MhC5mVPAVzC_OMrPpebKxgXG_c9r3csjbV8xjgyFZlr3YHGd5CFlFCS0E4mdDvA-RaLp9AGsNIliv5J-X18hBBPCaKHVbpulvjtRiEJpNZL_tpF10Lbq3UtmbwsLkQB_lDBEy6L1wyNaVLtiASDTR2bOPfc0gMsrLFf0gJgPmlsRhg_Vjciua3W3ndeSB4cmHBOIMH3w==&state=client123
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
https://kb-openbanking-oauth2.azurewebsites.net/?response_type=code&client_id= client&redirect_uri=REDIRECT_URI&scope=adaa&state=xyz
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
curl --location --request POST 'https://api.kb.cz/open/api/oauth2/v1/access_token' \
--header 'x-correlation-id: 9f1670dd-db08-4cbb-aa31-ac0454b42657' \
--header 'x-api-key: Bearer 3a7f779a-8cc1-364f-be2b-9ea161f63817' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode 'redirect_uri=https://app.kifli.cz/callback' \
--data-urlencode 'code=6W6hsrmHBqN8J6nEW3iPfbB97X8' \
--data-urlencode 'client_id=Kifli-1635' \
--data-urlencode 'client_secret=Xe-_BCRf9mi7uyEzIQiLGA' \
--data-urlencode 'grant_type=authorization_code'
```

## Response

```json
{
  "access_token": "eyJ0eXAiOiJKV1QiLCJraWQiOiJJTDdyR3BrMXNzNE9id0VIYmIrQ1RBbEozbzQ9IiwiYWxnIjoiUlMyNTYifQ.eyJzdWIiOiJBUElJRD0wZTYyNjQxMmJhYzg0Mzc4ODk0ZDFmNjM3MzQ4N2U4NiIsImN0cyI6Ik9BVVRIMl9TVEFURUxFU1NfR1JBTlQiLCJhdXRoX2xldmVsIjo0LCJhdWRpdFRyYWNraW5nSWQiOiIxY2YwY2I4Ni0xNDZmLTRhOTMtOWEzYS00YTQ3MmVkZDJiZmEtMTI3NTA1IiwiaXNzIjoiaHR0cHM6Ly91YXQyLWNhYXMua2IuY3ovb3BlbmFtL29hdXRoMiIsInRva2VuTmFtZSI6ImFjY2Vzc190b2tlbiIsInRva2VuX3R5cGUiOiJCZWFyZXIiLCJhdXRoR3JhbnRJZCI6IjFFd3VhZ1F0bDlvcV95eUg3OG1LWkYxdmxMOCIsImF1ZCI6IkFBQUF1dHB1dDMzQUItNDcwMSIsIm5iZiI6MTYzMTg2Nzg2NSwiZ3JhbnRfdHlwZSI6ImF1dGhvcml6YXRpb25fY29kZSIsInNjb3BlIjpbImNhcmRfZGF0YSIsImFkYWEiXSwiYXV0aF90aW1lIjoxNjMxODY3ODExLCJyZWFsbSI6Ii8iLCJleHAiOjE2Mzk2NDM4NjUsImlhdCI6MTYzMTg2Nzg2NSwiZXhwaXJlc19pbiI6Nzc3NjAwMCwianRpIjoiaklwQzJaQnZHOFdCRENMajd1elRYU2Y1UnRnIiwiY2Fhc09wZXJhdGlvbklkIjoiNDA1Y2Q0YWZiNzdmNDM1MTliNjljMmI1MTBhMmUxNWEifQ.McYFKolLFP4P2mybvgdtp3j5nv0dkZD_dRNKlBGDSSuYSifCvuYmt-F6ry1tkG3KsXNOqn1Jnb5hS6qwQpMMZr0lZOgUrbbPXUE-H2LB0-9C0Cv10kFK93faZmi__a3GRcC3KYYcYVykNmcGWTz7VBpt_yVme2Z7Piy5X718WNqPn2wd9dLhyW644Jpv0UA61GH361m80iJIOXjJPa0hY-xyOQ9-9ir1i8LObCI--YiQtGUOIa2t2K8qD8K4LBQCxy3Y-QW7ByDFBCP1n2a1wM_Vs3dZ6u9FsW0t-amOQTXiGBk_86zlR0Tgmn8zoYzv5KsL2qlzLVzWrx89eIySBg",
  "refresh_token": "eyJ0eXAiOiJKV1QiLCJraWQiOiJJTDdyR3BrMXNzNE9id0VIYmIrQ1RBbEozbzQ9IiwiYWxnIjoiUlMyNTYifQ.eyJzdWIiOiJBUElJRD0wZTYyNjQxMmJhYzg0Mzc4ODk0ZDFmNjM3MzQ4N2U4NiIsImN0cyI6Ik9BVVRIMl9TVEFURUxFU1NfR1JBTlQiLCJhdXRoX2xldmVsIjo0LCJhdWRpdFRyYWNraW5nSWQiOiIxY2YwY2I4Ni0xNDZmLTRhOTMtOWEzYS00YTQ3MmVkZDJiZmEtMTI3NTA0IiwiaXNzIjoiaHR0cHM6Ly91YXQyLWNhYXMua2IuY3ovb3BlbmFtL29hdXRoMiIsInRva2VuTmFtZSI6InJlZnJlc2hfdG9rZW4iLCJhdXRoTW9kdWxlcyI6IkNhYXNQYXNzd29yZHxPcGVyYXRpb25TdGF0ZUNoZWNrZXJ8UGlja2VyfE90cHxSZXF1ZXN0QmluZGVyfENhYXNBZGFwdGl2ZSIsInRva2VuX3R5cGUiOiJCZWFyZXIiLCJhdXRoR3JhbnRJZCI6IjFFd3VhZ1F0bDlvcV95eUg3OG1LWkYxdmxMOCIsImF1ZCI6IkFBQUF1dHB1dDMzQUItNDcwMSIsImFjciI6IjAiLCJuYmYiOjE2MzE4Njc4NjUsImdyYW50X3R5cGUiOiJhdXRob3JpemF0aW9uX2NvZGUiLCJzY29wZSI6WyJjYXJkX2RhdGEiLCJhZGFhIl0sImF1dGhfdGltZSI6MTYzMTg2NzgxMSwicmVhbG0iOiIvIiwiZXhwIjoxNjYzNDI0NzkxLCJpYXQiOjE2MzE4Njc4NjUsImV4cGlyZXNfaW4iOjMxNTU2OTI2LCJqdGkiOiI2a2NCNVBnLVJNTUlyN3YwLUhpRGFTaUltZWcifQ.ufH9vFCRGtJuctWdNDxcHaEbxbdAP_2vukeAzGNIofF-CATqp2gkBmwpOs0Fp75opYrslImoevGiUJ5DlbFiheyhL9N1rSTEPy2TmRgl8bd4_liJQVpp-yevH9eTyqsQkELkyCS-e0KGWeTcPfXe7PGQMwkneuiHGDLxNxyxVPg1qMXdApDdmLbIzoIxHDOIRA6eCR6uAwwOjgz3piJs8qLiBgykuTweE-zR1gSjQV-rPJknuf-GsntwwVCa3IwFA89tT9X_oh2bJQGhinFyHFvLclEWTCNU0ArFBkcZ6m9ez24r2WwflsBQFQw-lPfQ0DNuck33Op0c5VLbvQk8xw"
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
curl --location --request POST 'https://api.kb.cz/open/api/oauth2/v1/access_token' \
--header 'x-correlation-id: 9f1670dd-db08-4cbb-aa31-ac0454b42657' \
--header 'x-api-key: Bearer 3a7f779a-8cc1-364f-be2b-9ea161f63817' \
--header 'Content-Type: application/x-www-form-urlencoded' \
--data-urlencode 'redirect_uri=https://app.kifli.cz/callback' \
--data-urlencode 'client_id=Kifli-1635' \
--data-urlencode 'client_secret=Xe-_BCRf9mi7uyEzIQiLGA' \
--data-urlencode 'refresh_token=eyJ0eXAiOiJKV1QiLCJraWQiOiJ3RjJTa1I3NWMxamZsZ1VIOWJ6Wno3Tzllemc9IiwiYWxnIjoiUlMyNTYifQ.eyJzdWIiOiJBUElJRD01MmYwNDgyNjM3OTM0ZGZmOWY5MjE1MTBhMjlhMWYwYSIsImN0cyI6Ik9BVVRIMl9TVEFURUxFU1NfR1JBTlQiLCJhdXRoX2xldmVsIjo2LCJhdWRpdFRyYWNraW5nSWQiOiJlYzU5NDNjZi00ZGE4LTQ3ZDQtYjJmOS05ODNkMmQyYzE4MjEtMTU1ODg3MTgiLCJpc3MiOiJodHRwczovL2NhYXMua2IuY3o6NDQzL29wZW5hbS9vYXV0aDIiLCJ0b2tlbk5hbWUiOiJyZWZyZXNoX3Rva2VuIiwiYXV0aE1vZHVsZXMiOiJQYWFUfFBpY2tlcnxSZXF1ZXN0QmluZGVyfENhYXNBZGFwdGl2ZSIsInRva2VuX3R5cGUiOiJCZWFyZXIiLCJhdXRoR3JhbnRJZCI6IkFRNzBZcFduekpKTmFnc1h4S3BucmoxVWd3NCIsImF1ZCI6IktpZmxpLTE2MzUiLCJhY3IiOiIwIiwibmJmIjoxNjIzNzU3NDM0LCJncmFudF90eXBlIjoiYXV0aG9yaXphdGlvbl9jb2RlIiwic2NvcGUiOlsiYWRhYSJdLCJhdXRoX3RpbWUiOjE2MjM3NTczOTIsInJlYWxtIjoiLyIsImV4cCI6MTY1NTMxNDM2MCwiaWF0IjoxNjIzNzU3NDM0LCJleHBpcmVzX2luIjozMTU1NjkyNiwianRpIjoiNVhtYW4zbzNIb2lnaFlZZjJWS3RjRmNwUzZBIn0.0PbCum-UPt3E2Bq0xpvGB4LX29fLntiqeJP-lxpSSHt0fSEv_PmSkME19mpRaEod_grkWLtmnapphd2g2olQ_VeiRqYY_0v67De-D43E_tPm8Ei1dV_VBrqR0TJLtzLGRm8Gd7FtvSwNzc8Us3HyHlxU4yJfqCFTeln5xZzowgJ1kOLpUsG7BIClRyHvQwUAncPYF2Rx90_2IkW3Q18IIROSoA8CUajq18Yw8ulfFsMQ0xM_XB5aiUXnENUQYssSZTRL3xk5CTnm9F0I_p-u0Fa51l_Z-TU7CN5maKxJYETjFgMEa_dewSQ2x7AQoqC2LSrLggN0oHHlNyEJ_wP8rQ' \
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

```
curl --location --request GET 'https://gw.kbcloud.cz/sandbox/adaa/v1/accounts/' \
--header 'x-correlation-id: 3d9d62ff-17cb-4107-bf5a-f9ce8d0dff9a' \
--header 'x-api-key: Bearer 87e1330f-cee2-35fb-b290-dcfc2c21bb14' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJzdWIiOiJLQklEPXRlc3QiLCJhdWRpdFRyYWNraW5nSWQiOiJkNzQxMmZlNS1mZTczLTQ5NDUtYjc5Yy0wYmFmMDEyNzEyNWQiLCJpc3MiOiJodHRwczovL2xvZ2luLmtiLmN6L29wZW5hbS9vYXV0aDIiLCJ0b2tlbk5hbWUiOiJhY2Nlc3NfdG9rZW4iLCJ0b2tlbl90eXBlIjoiQmVhcmVyIiwiYXV0aEdyYW50SWQiOiI2YWNjNzYxZS1hODZlLTRkYjUtODU4YS1kZTBmZmIzNDIzNDEiLCJhdWQiOiIxMjM1NDYiLCJuYmYiOjE2Njg0Mjg0OTksInNjb3BlIjpbImFkYWEiXSwicmVhbG0iOiIvIiwiZXhwIjoxNjY4NDMyMDk5LCJpYXQiOjE2Njg0Mjg0OTksImV4cGlyZXNfaW4iOjM2MDAwMDAsImp0aSI6IjE2NGNmZWE4LTQ2MGYtNDBjYS1hMTRjLWJlNTZjNmY1YjBjNiJ9.-MYDD540bx4rCgFPVVd9FruDHuCrwkDmv5OqbDW7vjQ' \
--data-raw ''
```

## Response

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
