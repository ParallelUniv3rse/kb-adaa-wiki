# Application Registration - OAuth2

```json
{
  "clientName": "Nejlepší produkt",
  "clientNameEn": "Best product",
  "applicationType": "web",
  "redirectUris": ["https://client.example.org/callback"],

  "scope": ["adaa", "bpisp", "card_data"],
  "encryptionKey": "djh5L0I/RShHK0tiUGVTaFZtWXEzdDZ3OXokQyZGKUo\u003d",
  "encryptionAlg": "AES-256",

  "softwareStatement": "eyJhbGciOiJIUzI1NiJ9.eyJ2ZW5kb3JOYW1lIjoiQ29tcGFueSBhLnMuIiwic29mdHdhcmVOYW1lIjoiTmVqbGVwxaHDrSBwcm9kdWt0Iiwic29mdHdhcmVOYW1lRW4iOiJCZXN0IHByb2R1Y3QiLCJzb2Z0d2FyZUlkIjoiZjY0YmYyZTQ0N2U1NDUyMjhjNzhlMDdiMDgxYTgyZWUiLCJzb2Z0d2FyZVZlcnNpb24iOiIxLjAiLCJzb2Z0d2FyZVVyaSI6Imh0dHBzOi8vY2xpZW50LmV4YW1wbGUub3JnIiwicmVkaXJlY3RVcmlzIjpbImh0dHBzOi8vY2xpZW50LmV4YW1wbGUub3JnL2NhbGxiYWNrIiwiaHR0cHM6Ly9jbGllbnQuZXhhbXBsZS5vcmcvY2FsbGJhY2stYmFja3VwIl0sInRva2VuRW5kcG9pbnRBdXRoTWV0aG9kIjoiY2xpZW50X3NlY3JldF9wb3N0IiwiZ3JhbnRUeXBlcyI6WyJhdXRob3JpemF0aW9uX2NvZGUiXSwicmVzcG9uc2VUeXBlcyI6WyJjb2RlIl0sInJlZ2lzdHJhdGlvbkJhY2tVcmkiOiJodHRwczovL2NsaWVudC5leGFtcGxlLm9yZy9iYWNrdXJpIiwiY29udGFjdHMiOlsiZW1haWw6IGV4YW1wbGVAZ29vZHNvZnQuY29tIl0sImxvZ29VcmkiOiJodHRwczovL2NsaWVudC5leGFtcGxlLm9yZy9sb2dvLnBuZyIsInRvc1VyaSI6Imh0dHBzOi8vY2xpZW50LmV4YW1wbGUub3JnL3RvcyIsInBvbGljeVVyaSI6Imh0dHBzOi8vY2xpZW50LmV4YW1wbGUub3JnL3BvbGljeSJ9.Fw11ePNty7aimkm3yBYMoK5L-8Blpec4CafNJ-giC4g"
}
```

## Attributes

### Scopes

- adaa - account direct access api
- bpisp - batch payments
- card_data - information about card

### Statements

- Statement from previous step - [software statement](./Software-Statements)

## Convert to BASE64

```
ewrCoCDCoMKgImNsaWVudE5hbWUiOsKgIk5lamxlcMWhw60gcHJvZHVrdCIsCsKgIMKgwqAiY2xpZW50TmFtZUVuIjrCoCJCZXN0IHByb2R1Y3QiLArCoCDCoMKgImFwcGxpY2F0aW9uVHlwZSI6wqAid2ViIiwKwqAgwqDCoCJyZWRpcmVjdFVyaXMiOiBbCsKgIMKgIMKgIMKgwqBbaHR0cHM6Ly9jbGllbnQuZXhhbXBsZS5vcmcvY2FsbGJhY2tdKGh0dHBzOi8vY2xpZW50LmV4YW1wbGUub3JnL2NhbGxiYWNrICJodHRwczovL2NsaWVudC5leGFtcGxlLm9yZy9jYWxsYmFjayIpCsKgIMKgIF0sCsKgIMKgwqAic2NvcGUiOiBbCsKgIMKgIMKgIMKgwqAiYWRhYSIswqAiYnBpc3AiLMKgImNhcmRfZGF0YSIKwqAgwqAgXSwKwqAgwqDCoCJlbmNyeXB0aW9uS2V5IjrCoCJkamg1TDBJL1JTaEhLMHRpVUdWVGFGWnRXWEV6ZERaM09Yb2tReVpHS1VvPSIsCsKgIMKgwqAiZW5jcnlwdGlvbkFsZyI6wqAiQUVTLTI1NiIsIArCoMKgInNvZnR3YXJlU3RhdGVtZW50IjrCoCJleUpoYkdjaU9pSklVekkxTmlKOS5leUoyWlc1a2IzSk9ZVzFsSWpvaVEyOXRjR0Z1ZVNCaExuTXVJaXdpYzI5bWRIZGhjbVZPWVcxbElqb2lUbVZxYkdWd3hhSERyU0J3Y205a2RXdDBJaXdpYzI5bWRIZGhjbVZPWVcxbFJXNGlPaUpDWlhOMElIQnliMlIxWTNRaUxDSnpiMlowZDJGeVpVbGtJam9pWmpZMFltWXlaVFEwTjJVMU5EVXlNamhqTnpobE1EZGlNRGd4WVRneVpXVWlMQ0p6YjJaMGQyRnlaVlpsY25OcGIyNGlPaUl4TGpBaUxDSnpiMlowZDJGeVpWVnlhU0k2SW1oMGRIQnpPaTh2WTJ4cFpXNTBMbVY0WVcxd2JHVXViM0puSWl3aWNtVmthWEpsWTNSVmNtbHpJanBiSW1oMGRIQnpPaTh2WTJ4cFpXNTBMbVY0WVcxd2JHVXViM0puTDJOaGJHeGlZV05ySWl3aWFIUjBjSE02THk5amJHbGxiblF1WlhoaGJYQnNaUzV2Y21jdlkyRnNiR0poWTJzdFltRmphM1Z3SWwwc0luUnZhMlZ1Ulc1a2NHOXBiblJCZFhSb1RXVjBhRzlrSWpvaVkyeHBaVzUwWDNObFkzSmxkRjl3YjNOMElpd2laM0poYm5SVWVYQmxjeUk2V3lKaGRYUm9iM0pwZW1GMGFXOXVYMk52WkdVaVhTd2ljbVZ6Y0c5dWMyVlVlWEJsY3lJNld5SmpiMlJsSWwwc0luSmxaMmx6ZEhKaGRHbHZia0poWTJ0VmNta2lPaUpvZEhSd2N6b3ZMMk5zYVdWdWRDNWxlR0Z0Y0d4bExtOXlaeTlpWVdOcmRYSnBJaXdpWTI5dWRHRmpkSE1pT2xzaVpXMWhhV3c2SUdWNFlXMXdiR1ZBWjI5dlpITnZablF1WTI5dElsMHNJbXh2WjI5VmNta2lPaUpvZEhSd2N6b3ZMMk5zYVdWdWRDNWxlR0Z0Y0d4bExtOXlaeTlzYjJkdkxuQnVaeUlzSW5SdmMxVnlhU0k2SW1oMGRIQnpPaTh2WTJ4cFpXNTBMbVY0WVcxd2JHVXViM0puTDNSdmN5SXNJbkJ2YkdsamVWVnlhU0k2SW1oMGRIQnpPaTh2WTJ4cFpXNTBMbVY0WVcxd2JHVXViM0puTDNCdmJHbGplU0o5LkZ3MTFlUE50eTdhaW1rbTN5QllNb0s1TC04QmxwZWM0Q2FmTkotZ2lDNGciCn0;
```

## Request

ℹ️ This request put in your browser

```
GET
https://api.kb.cz/client-registration/saml/register?registrationRequest=ewrCoCDCoMKgImNsaWVudE5hbWUiOsKgIk5lamxlcMWhw60gcHJvZHVrdCIsCsKgIMKgwqAiY2xpZW50TmFtZUVuIjrCoCJCZXN0IHByb2R1Y3QiLArCoCDCoMKgImFwcGxpY2F0aW9uVHlwZSI6wqAid2ViIiwKwqAgwqDCoCJyZWRpcmVjdFVyaXMiOiBbCsKgIMKgIMKgIMKgwqBbaHR0cHM6Ly9jbGllbnQuZXhhbXBsZS5vcmcvY2FsbGJhY2tdKGh0dHBzOi8vY2xpZW50LmV4YW1wbGUub3JnL2NhbGxiYWNrICJodHRwczovL2NsaWVudC5leGFtcGxlLm9yZy9jYWxsYmFjayIpCsKgIMKgIF0sCsKgIMKgwqAic2NvcGUiOiBbCsKgIMKgIMKgIMKgwqAiYWRhYSIswqAiYnBpc3AiLMKgImNhcmRfZGF0YSIKwqAgwqAgXSwKwqAgwqDCoCJlbmNyeXB0aW9uS2V5IjrCoCJkamg1TDBJL1JTaEhLMHRpVUdWVGFGWnRXWEV6ZERaM09Yb2tReVpHS1VvPSIsCsKgIMKgwqAiZW5jcnlwdGlvbkFsZyI6wqAiQUVTLTI1NiIsIArCoMKgInNvZnR3YXJlU3RhdGVtZW50IjrCoCJleUpoYkdjaU9pSklVekkxTmlKOS5leUoyWlc1a2IzSk9ZVzFsSWpvaVEyOXRjR0Z1ZVNCaExuTXVJaXdpYzI5bWRIZGhjbVZPWVcxbElqb2lUbVZxYkdWd3hhSERyU0J3Y205a2RXdDBJaXdpYzI5bWRIZGhjbVZPWVcxbFJXNGlPaUpDWlhOMElIQnliMlIxWTNRaUxDSnpiMlowZDJGeVpVbGtJam9pWmpZMFltWXlaVFEwTjJVMU5EVXlNamhqTnpobE1EZGlNRGd4WVRneVpXVWlMQ0p6YjJaMGQyRnlaVlpsY25OcGIyNGlPaUl4TGpBaUxDSnpiMlowZDJGeVpWVnlhU0k2SW1oMGRIQnpPaTh2WTJ4cFpXNTBMbVY0WVcxd2JHVXViM0puSWl3aWNtVmthWEpsWTNSVmNtbHpJanBiSW1oMGRIQnpPaTh2WTJ4cFpXNTBMbVY0WVcxd2JHVXViM0puTDJOaGJHeGlZV05ySWl3aWFIUjBjSE02THk5amJHbGxiblF1WlhoaGJYQnNaUzV2Y21jdlkyRnNiR0poWTJzdFltRmphM1Z3SWwwc0luUnZhMlZ1Ulc1a2NHOXBiblJCZFhSb1RXVjBhRzlrSWpvaVkyeHBaVzUwWDNObFkzSmxkRjl3YjNOMElpd2laM0poYm5SVWVYQmxjeUk2V3lKaGRYUm9iM0pwZW1GMGFXOXVYMk52WkdVaVhTd2ljbVZ6Y0c5dWMyVlVlWEJsY3lJNld5SmpiMlJsSWwwc0luSmxaMmx6ZEhKaGRHbHZia0poWTJ0VmNta2lPaUpvZEhSd2N6b3ZMMk5zYVdWdWRDNWxlR0Z0Y0d4bExtOXlaeTlpWVdOcmRYSnBJaXdpWTI5dWRHRmpkSE1pT2xzaVpXMWhhV3c2SUdWNFlXMXdiR1ZBWjI5dlpITnZablF1WTI5dElsMHNJbXh2WjI5VmNta2lPaUpvZEhSd2N6b3ZMMk5zYVdWdWRDNWxlR0Z0Y0d4bExtOXlaeTlzYjJkdkxuQnVaeUlzSW5SdmMxVnlhU0k2SW1oMGRIQnpPaTh2WTJ4cFpXNTBMbVY0WVcxd2JHVXViM0puTDNSdmN5SXNJbkJ2YkdsamVWVnlhU0k2SW1oMGRIQnpPaTh2WTJ4cFpXNTBMbVY0WVcxd2JHVXViM0puTDNCdmJHbGplU0o5LkZ3MTFlUE50eTdhaW1rbTN5QllNb0s1TC04QmxwZWM0Q2FmTkotZ2lDNGciCn0=&state=client123
```

> Identification request
>
> Use parameter "state", the parameter state get back with response

## Response

```
302 Found
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

---

[Continue to Tokens...](./Tokens)
