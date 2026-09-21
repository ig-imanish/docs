# Source: https://docs.umami.is/docs/api-reference/get-my-api-keys

Menu

Account

# List my API keys

Copy page

GET`/api/me/api-keys`

Returns metadata for the current user's API keys. Available on self-hosted installations.

## Headers

| Name | Type | Description |
| --- | --- | --- |
| Authorizationrequired | string | Authentication credentials, e.g. `Bearer <token>`. |

## Responses

200The operation completed successfully.

| Name | Type | Description |
| --- | --- | --- |
| createdAtrequired | string | Date and time the record was created. |
| idrequired | string | Unique identifier of the resource. |
| keyPrefixrequired | string | Visible prefix used to identify an API key. |
| lastUsedAtrequired | string | Date and time the credential was last used. |
| namerequired | string | Display name of the resource. |

200 example

```json
[
  {
    "createdAt": "2024-01-15T09:30:00Z",
    "id": "string",
    "keyPrefix": "string",
    "lastUsedAt": "2024-01-15T09:30:00Z",
    "name": "string"
  }
]
```

401Unauthorized.

| Name | Type | Description |
| --- | --- | --- |
| errorrequired | object | Error details returned when the operation fails. |
| 
properties

 |

401 example

```json
{
  "error": {
    "code": "unauthorized",
    "message": "Unauthorized.",
    "status": 401
  }
}
```

404Not found.

| Name | Type | Description |
| --- | --- | --- |
| errorrequired | object | Error details returned when the operation fails. |
| 
properties

 |

404 example

```json
{
  "error": {
    "code": "not-found",
    "message": "Not found.",
    "status": 404
  }
}
```

## Code samples

cURLJavaScriptPython

cURL

```bash
curl -X GET 'https://api.example.com/api/me/api-keys' \
  -H 'Authorization: Bearer <token>'
```

[PreviousGet my authentication details](https://docs.umami.is/docs/api-reference/get-me) [NextList my team memberships](https://docs.umami.is/docs/api-reference/get-my-teams)

On this page