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

> **Certificates in Postman** - [How to add certificate in Postman](https://learning.postman.com/docs/sending-requests/certificates/#adding-client-certificates)
> **TLS configuration of JAX-RS Client** - [adaa-example-spring-boot](https://github.com/komercka/adaa-example-spring-boot/blob/e4c07ac5f4166a4199a0d2fc8dc01392d888e4e2/web/src/main/java/cz/kb/openbanking/adaa/example/springboot/web/configuration/WebConfiguration.java#L37)

```js
curl --cert-type P12 cert.p12:password --location --request POST 'https://api.kb.cz/open/api/client-registration/v1/software-statements' \
--header 'x-correlation-id: 42c0e667-0f5e-4900-9f5e-fd707e35ba75' \
--header 'x-api-key: Bearer 3a7f779a-8cc1-364f-be2b-9ea161f63817' \
--header 'Content-Type: application/json' \
--data-raw '{
    "softwareName": "example app",
    "softwareNameEn": "example app",
    "softwareId": "f64bf2e447e545228c78e07b091a82ee",
    "softwareVersion": "1.0",
    "softwareUri": "https://client.example.org",
    "redirectUris": [
        "https://client.example.org/callback",
        "https://client.example.org/callback-backup"
    ],
    "tokenEndpointAuthMethod": "client_secret_post",
    "grantTypes": [
        "authorization_code",
        "refresh_token"
    ],
    "responseTypes": [
        "code"
    ],
    "registrationBackUri": "https://client.example.org/backuri",
    "contacts": [
        "email: hello@example.org"
    ],
    "logoUri": "https://client.example.org/icon.png",
    "tosUri": "https://client.example.org/tos",
    "policyUri": "https://client.example.org/policy"
}'
```

or

```js
curl --cert  client.crt --key client.key --cacert ca.crt https://api.kb.cz/open/api/client-registration/v1/software-statements
```

## Response

> **Check information in JWT token**
> You can check content JWT token on [jwt.io](https://jwt.io)

```
eyJhbGciOiJSUzI1NiJ9.eyJpc3MiOiJLb21lcsSNbsOtIEJhbmthIGEucy4iLCJpYXQiOjE2NTU3MjYzMzMsImV4cCI6MTY4NzI2MjMzMywidmVuZG9yTmFtZSI6IkJsb2szNyBzLnIuby4iLCJ2ZW5kb3JSZWdpc3RyYXRpb25OdW1iZXIiOiIwNTQzNTg3MSIsInNvZnR3YXJlTmFtZSI6ImV4YW1wbGUgYXBwIiwic29mdHdhcmVOYW1lRW4iOiJleGFtcGxlIGFwcCIsInNvZnR3YXJlSWQiOiJmNjRiZjJlNDQ3ZTU0NTIyOGM3OGUwN2IwOTFhODJlZSIsInNvZnR3YXJlVmVyc2lvbiI6IjEuMCIsInNvZnR3YXJlVXJpIjoiaHR0cHM6Ly9jbGllbnQuZXhhbXBsZS5vcmciLCJyZWRpcmVjdFVyaXMiOlsiaHR0cHM6Ly9jbGllbnQuZXhhbXBsZS5vcmcvY2FsbGJhY2siLCJodHRwczovL2NsaWVudC5leGFtcGxlLm9yZy9jYWxsYmFjay1iYWNrdXAiXSwidG9rZW5FbmRwb2ludEF1dGhNZXRob2QiOiJjbGllbnRfc2VjcmV0X3Bvc3QiLCJncmFudFR5cGVzIjpbImF1dGhvcml6YXRpb25fY29kZSIsInJlZnJlc2hfdG9rZW4iXSwicmVzcG9uc2VUeXBlcyI6WyJjb2RlIl0sInJlZ2lzdHJhdGlvbkJhY2tVcmkiOiJodHRwczovL2NsaWVudC5leGFtcGxlLm9yZy9iYWNrdXJpIiwiY29udGFjdHMiOlsiZW1haWw6IGhlbGxvQGV4YW1wbGUub3JnIl0sImxvZ29VcmkiOiJodHRwczovL2NsaWVudC5leGFtcGxlLm9yZy9pY29uLnBuZyIsInRvc1VyaSI6Imh0dHBzOi8vY2xpZW50LmV4YW1wbGUub3JnL3RvcyIsInBvbGljeVVyaSI6Imh0dHBzOi8vY2xpZW50LmV4YW1wbGUub3JnL3BvbGljeSJ9.hd016urrIl2o7LsqXKqoDXODI8DSY8aYZHzTs7j451i3BQ0lVu64jty4EYMV7Q8gGgrx5IN6lk1QwZmIpIz9dReIMEbQHiHxogAgrjln4mPSGf0x2b_YbsEKLMiCh27ZlhmNTHIBr9jq9mIo9Ab9wWViUAAAc00dmtXQdC84Zm67nIP5KDCiRTExAPLVpJqES8lYZbqlTIVQ6D_EKrGybxB0QP5b5bjOYKwyu7c5ZwehUGAuCf3zOWZUEKQuxUHoi0cVvAUZ0L8EJelcgM_8iO0cE1GVpsnxk_8YPcWtfh6h1OARUGGZHR_t_3W1i9NfrFGguOs5AOgG6i8QA
```

---

[Continue to Application Registration - OAuth2...](./Application-Registration-OAuth2)
