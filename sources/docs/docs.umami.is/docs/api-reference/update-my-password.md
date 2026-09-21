# Source: https://docs.umami.is/docs/api-reference/update-my-password

Menu

Account

# Change my password

Copy page

POST`/api/me/password`

Verifies the current password and replaces it with the supplied new password.

## Headers

| Name | Type | Description |
| --- | --- | --- |
| Authorizationrequired | string | Authentication credentials, e.g. `Bearer <token>`. |

## Request body

| Name | Type | Description |
| --- | --- | --- |
| currentPasswordrequired | string | Current account password. |
| newPasswordrequired | string | New password to set for the account. |

Example request

```json
{
  "currentPassword": "string",
  "newPassword": "string"
}
```

## Responses

200The operation completed successfully.

| Name | Type | Description |
| --- | --- | --- |
| createdAtrequired | string | Date and time the record was created. |
| idrequired | string | Unique identifier of the resource. |
| rolerequired | string | Permission role assigned to the user. |
| usernamerequired | string | Username of the account. |

200 example

```json
{
  "createdAt": "2024-01-15T09:30:00Z",
  "id": "string",
  "role": "string",
  "username": "string"
}
```

400Bad request.

| Name | Type | Description |
| --- | --- | --- |
| errorrequired | object | Error details returned when the operation fails. |
| 
properties

 |

400 example

```json
{
  "error": {
    "code": "bad-request",
    "message": "Bad request.",
    "status": 400
  }
}
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

## Code samples

cURLJavaScriptPython

cURL

```bash
curl -X POST 'https://api.example.com/api/me/password' \
  -H 'Authorization: Bearer <token>' \
  -H 'Content-Type: application/json' \
  -d '{
  "currentPassword": "string",
  "newPassword": "string"
}'
```

[PreviousCommon endpoints](https://docs.umami.is/docs/api/common-endpoints) [NextCreate an API key](https://docs.umami.is/docs/api-reference/create-my-api-key)

On this page