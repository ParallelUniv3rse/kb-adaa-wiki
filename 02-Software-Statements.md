# Software Statements

[//]: # (TODO: add links to the Sandbox and Production API docs)

> **JWT tokens validity**
>
> - The JWT statement is valid for 12 months
> - Please fill in the email field, we will contact you about updates or tokens validity

## Prerequisites for getting the Software statement

1) You own a Qualified certificate from one of the following CAs:
> - I.CA
> - PostSignum

## Request

**Sandbox** `https://api-gateway.kb.cz/sandbox/client-registration/v2/software-statements` \
**Production** `https://api-gateway.kb.cz/client-registration/v2/software-statements` 


> **Certificates in Postman** - [How to add certificate in Postman](https://learning.postman.com/docs/sending-requests/certificates/#adding-client-certificates)
>
> **TLS configuration of JAX-RS Client** - [adaa-example-spring-boot](https://github.com/komercka/adaa-example-spring-boot/blob/e4c07ac5f4166a4199a0d2fc8dc01392d888e4e2/web/src/main/java/cz/kb/openbanking/adaa/example/springboot/web/configuration/WebConfiguration.java#L37)

<details id="curl-example"><summary>Client TLS Authentication Example - Curl</summary>

```js
curl -v --cert-type P12 --cert cert.p12:password --location --request POST 'https://api-gateway.kb.cz/client-registration/v2/software-statements' \
--header 'x-correlation-id: 42c0e667-0f5e-4900-9f5e-fd707e35ba75' \
--header 'apiKey 3a7f779a-8cc1-364f-be2b-9ea161f63817' \
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
curl --cert  client.crt --key client.key --cacert ca.crt https://api-gateway.kb.cz/client-registration/v2/software-statements
```

</details>

<details id="c-sharp-example"><summary>Client TLS Authentication Example - C# 10 .NET6</summary>

```cs
using System.Net.Mime;
using System.Security.Cryptography;
using System.Security.Cryptography.X509Certificates;
using System.Text;
namespace SoftwareStatementRegistrationExample
{
    /// <summary>
    /// Example of Software Statement registration over Client Registration API demonstrating client TLS authentication with a certificate issued without client auth key usage extension. This code example is not intended for use in production.
    /// </summary>
    class SoftwareStatementRegistrationExample
    {
        // OID of enhanced/extended key usage extension, see https://oidref.com/1.3.6.1.5.5.7.3.2
        private const string ClientAuthOid = "1.3.6.1.5.5.7.3.2";
        // self-signed PFX certificate with digital signature key usage extension but without client auth encoded as Base64, see https://datatracker.ietf.org/doc/html/rfc4648#section-4
        private const string CertificateBase64 = "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";
        // password of the self-signed certificate
        private const string CertificatePassword = "password";
        // JSON software metadata encoded as Base64 see https://datatracker.ietf.org/doc/html/rfc4648#section-4
        private const string SoftwareStatementBodyBase64 = "ew0KICAic29mdHdhcmVOYW1lIjogIkV4YW1wbGVDbGllbnQiLA0KICAic29mdHdhcmVOYW1lRW4iOiAiRXhhbXBsZUNsaWVudCIsDQogICJzb2Z0d2FyZUlkIjogIjkzZDQ5MmI5ZDQ2ODQwZTM4MDlhNzQ1MzFkMTQ0OTEyIiwNCiAgInNvZnR3YXJlVmVyc2lvbiI6ICIxLjAiLA0KICAic29mdHdhcmVVcmkiOiAiaHR0cHM6Ly9jbGllbnQuZXhhbXBsZS5vcmciLA0KICAicmVkaXJlY3RVcmlzIjogWw0KICAgICJodHRwczovL2NsaWVudC5leGFtcGxlLm9yZy9jYWxsYmFjayIsDQogICAgImh0dHBzOi8vY2xpZW50LmV4YW1wbGUub3JnL2NhbGxiYWNrLWJhY2t1cCINCiAgXSwNCiAgInRva2VuRW5kcG9pbnRBdXRoTWV0aG9kIjogImNsaWVudF9zZWNyZXRfYmFzaWMiLA0KICAiZ3JhbnRUeXBlcyI6IFsNCiAgICAiYXV0aG9yaXphdGlvbl9jb2RlIiwNCiAgICAicmVmcmVzaF90b2tlbiINCiAgXSwNCiAgInJlc3BvbnNlVHlwZXMiOiBbDQogICAgImNvZGUiDQogIF0sDQogICJyZWdpc3RyYXRpb25CYWNrVXJpIjogImh0dHBzOi8vY2xpZW50LmV4YW1wbGUub3JnL2JhY2t1cmkiLA0KICAiY29udGFjdHMiOiBbDQogICAgImVtYWlsOiBleGFtcGxlQGV4YW1wbGUuY29tIg0KICBdLA0KICAibG9nb1VyaSI6ICJodHRwczovL2NsaWVudC5leGFtcGxlLm9yZy9sb2dvLnBuZyIsDQogICJ0b3NVcmkiOiAiaHR0cHM6Ly9jbGllbnQuZXhhbXBsZS5vcmcvdG9zIiwNCiAgInBvbGljeVVyaSI6ICJodHRwczovL2NsaWVudC5leGFtcGxlLm9yZy9wb2xpY3kiDQp9";
        // URL of Client Registration API, software-statements endpoint
        private const string SoftwareStatementUrl = "https://api-gateway.kb.cz/client-registration/v2/software-statements";
        // header name of correlation ID
        private const string CorrelationIdHeaderName = "x-correlation-id";
        // header name of API key
        private const string ApiKeyHeaderName = "apiKey";
        // mock value of API key header
        private const string ApiKey = "api-key-mock";

        /// <summary>
        /// Main entrypoint for the Software Statement Registration Example.
        /// </summary>
        /// <param name="args">the optional arguments, irrelevant to the example</param>
        static void Main(string[] args)
        {
            // decode Base64 string to byte array
            byte[] certificateBytes = Convert.FromBase64String(CertificateBase64);
            // instantiate X509Certificate2 class
            X509Certificate2 certificate = new X509Certificate2(certificateBytes, CertificatePassword);
            // replace certificate's key usage with a client auth extension due to .NET6 platform requiring correct key usage extension for client TLS authentication
            ReplaceKeyUsageWithClientAuth(certificate);
            // decode Base64 string to UTF8 encoded string
            string softwareStatementBodyJson = Encoding.UTF8.GetString(Convert.FromBase64String(SoftwareStatementBodyBase64));
            // initialize a dictionary representing http headers
            IDictionary<string, string> headers = new Dictionary<string, string>
            {
                { ApiKeyHeaderName, ApiKey },
                { CorrelationIdHeaderName, Guid.NewGuid().ToString() }
            };
            // execute a POST request specified by given URL, JSON body and headers with client TLS authentication
            HttpResponseMessage response = PostJsonOverTlsClientAuth(SoftwareStatementUrl, softwareStatementBodyJson, headers, certificate);
            // output the response to console - expecting status code "403 Forbidden" due to a self-signed certificate
            Console.WriteLine(response);
            // output the response's body to console - expecting message "Invalid certificate or token" due to a self-signed certificate
            Console.WriteLine(response.Content.ReadAsStringAsync().GetAwaiter().GetResult());
        }


        /// <summary>
        /// Replace existing key usage extensions with a valid client auth key usage extensions of a given certificate.
        /// </summary>
        /// <param name="certificate">the certificate for key usage extensions replacement</param>
        private static void ReplaceKeyUsageWithClientAuth(X509Certificate2 certificate)
        {
            foreach (var extension in certificate.Extensions)
            {
                if (extension.GetType() == typeof(X509KeyUsageExtension))
                {
                    // replace key usage extension with one with valid flags for client TLS authentication
                    X509KeyUsageExtension keyUsageExtension = new X509KeyUsageExtension(X509KeyUsageFlags.DigitalSignature | X509KeyUsageFlags.KeyEncipherment, false);
                    extension.RawData = keyUsageExtension.RawData;
                } else if (extension.GetType() == typeof(X509EnhancedKeyUsageExtension))
                {
                    // replace enhanced/extended key usage extension with one with valid flags for client TLS authentication
                    X509EnhancedKeyUsageExtension enhancedKeyUsageExtension = new X509EnhancedKeyUsageExtension(new OidCollection() { Oid.FromOidValue(ClientAuthOid, OidGroup.EnhancedKeyUsage) }, false);
                    extension.RawData = enhancedKeyUsageExtension.RawData;
                }
            }
        }

        /// <summary>
        /// Execute a POST request specified by given URL, JSON body and headers with client TLS authentication.
        /// </summary>
        /// <param name="url">the URL to make a POST request to</param>
        /// <param name="json">the JSON for a POST request body</param>
        /// <param name="headers">the headers to send along the POST request</param>
        /// <param name="certificate">the certificate for the client TLS authentication of the POST request</param>
        /// <returns>The response of the POST request.</returns>
        private static HttpResponseMessage PostJsonOverTlsClientAuth(string url, string json, IDictionary<string, string> headers, X509Certificate2 certificate)
        {
            var handler = new HttpClientHandler();
            handler.ClientCertificates.Add(certificate);

            var client = new HttpClient(handler);

            var content = new StringContent(json, Encoding.UTF8, MediaTypeNames.Application.Json);
            headers.ToList().ForEach(header => content.Headers.Add(header.Key, header.Value));

            return client.PostAsync(url, content).GetAwaiter().GetResult();    
        }
    }
}
```

</details>

<details id="js-example"><summary>Client TLS Authentication Example - NodeJS</summary>

```js
const { v4: uuidv4 } = require('uuid')
const https = require('https')
const fs = require('fs')
const path = require('path')

const pfxFile = fs.readFileSync(path.resolve('./ePecet_certificate_22_23.pfx'))

const sslConfigureAgent = new https.Agent({
  pfx: pfxFile,
  passphrase: 'your-cert-passphrase',
})

const myHeaders = new fetch.Headers()
myHeaders.append('apiKey', 'mock-api-key')
myHeaders.append('x-correlation-id', uuidv4())
myHeaders.append('Content-Type', 'application/json')

const requestOptions = {
  method: 'POST',
  headers: myHeaders,
  body: raw,
  redirect: 'follow',
  agent: sslConfigureAgent,
}

const response = await fetch(
  'https://client-registration.api-gateway.kb.cz/v2/software-statements',
  requestOptions,
)
```


</details>

## Response
The software statement is returned as a JWT token in the Response body.

> **Check information in the JWT token** \
> For debugging, you can check the content of the JWT token on [jwt.io](https://jwt.io)

Example token from a response:
```
eyJhbGciOiJSUzI1NiJ9.eyJpc3MiOiJLb21lcsSNbsOtIEJhbmthIGEucy4iLCJpYXQiOjE2NTU3MjYzMzMsImV4cCI6MTY4NzI2MjMzMywidmVuZG9yTmFtZSI6IkJsb2szNyBzLnIuby4iLCJ2ZW5kb3JSZWdpc3RyYXRpb25OdW1iZXIiOiIwNTQzNTg3MSIsInNvZnR3YXJlTmFtZSI6ImV4YW1wbGUgYXBwIiwic29mdHdhcmVOYW1lRW4iOiJleGFtcGxlIGFwcCIsInNvZnR3YXJlSWQiOiJmNjRiZjJlNDQ3ZTU0NTIyOGM3OGUwN2IwOTFhODJlZSIsInNvZnR3YXJlVmVyc2lvbiI6IjEuMCIsInNvZnR3YXJlVXJpIjoiaHR0cHM6Ly9jbGllbnQuZXhhbXBsZS5vcmciLCJyZWRpcmVjdFVyaXMiOlsiaHR0cHM6Ly9jbGllbnQuZXhhbXBsZS5vcmcvY2FsbGJhY2siLCJodHRwczovL2NsaWVudC5leGFtcGxlLm9yZy9jYWxsYmFjay1iYWNrdXAiXSwidG9rZW5FbmRwb2ludEF1dGhNZXRob2QiOiJjbGllbnRfc2VjcmV0X3Bvc3QiLCJncmFudFR5cGVzIjpbImF1dGhvcml6YXRpb25fY29kZSIsInJlZnJlc2hfdG9rZW4iXSwicmVzcG9uc2VUeXBlcyI6WyJjb2RlIl0sInJlZ2lzdHJhdGlvbkJhY2tVcmkiOiJodHRwczovL2NsaWVudC5leGFtcGxlLm9yZy9iYWNrdXJpIiwiY29udGFjdHMiOlsiZW1haWw6IGhlbGxvQGV4YW1wbGUub3JnIl0sImxvZ29VcmkiOiJodHRwczovL2NsaWVudC5leGFtcGxlLm9yZy9pY29uLnBuZyIsInRvc1VyaSI6Imh0dHBzOi8vY2xpZW50LmV4YW1wbGUub3JnL3RvcyIsInBvbGljeVVyaSI6Imh0dHBzOi8vY2xpZW50LmV4YW1wbGUub3JnL3BvbGljeSJ9.hd016urrIl2o7LsqXKqoDXODI8DSY8aYZHzTs7j451i3BQ0lVu64jty4EYMV7Q8gGgrx5IN6lk1QwZmIpIz9dReIMEbQHiHxogAgrjln4mPSGf0x2b_YbsEKLMiCh27ZlhmNTHIBr9jq9mIo9Ab9wWViUAAAc00dmtXQdC84Zm67nIP5KDCiRTExAPLVpJqES8lYZbqlTIVQ6D_EKrGybxB0QP5b5bjOYKwyu7c5ZwehUGAuCf3zOWZUEKQuxUHoi0cVvAUZ0L8EJelcgM_8iO0cE1GVpsnxk_8YPcWtfh6h1OARUGGZHR_t_3W1i9NfrFGguOs5AOgG6i8QA
```

## Troubleshooting
>
> **Missing mutual TLS configuration**
>
> In case of error response due to an invalid mutual TLS configuration, please [confirm a certificate was sent](https://learning.postman.com/docs/sending-requests/certificates/#confirming-a-certificate-was-sent).

```js
{
    "errors": [
        {
            "error": "UNAUTHORISED",
            "message": "Missing certificate or access token"
        }
    ]
}
```

---

## Next step
[Continue to Application Registration - OAuth2...](./03-Application-Registration-OAuth2)
