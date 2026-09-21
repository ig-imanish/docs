# Source: https://docs.umami.is/docs/api-reference/create-my-api-key

Menu

Account

# Create an API key

Copy page

POST`/api/me/api-keys`

Creates a named API key for the current user and returns its secret value. Available on self-hosted installations.

## Headers

| Name | Type | Description |
| --- | --- | --- |
| Authorizationrequired | string | Authentication credentials, e.g. `Bearer <token>`. |

## Request body

| Name | Type | Description |
| --- | --- | --- |
| namerequired | any | Display name of the resource. |

Example request

```json
{
  "name": {}
}
```

## Responses

200The operation completed successfully.

| Name | Type | Description |
| --- | --- | --- |
| createdAtrequired | string | Date and time the record was created. |
| idrequired | string | Unique identifier of the resource. |
| keyrequired | string | |
| keyPrefixrequired | string | Visible prefix used to identify an API key. |
| namerequired | string | Display name of the resource. |

200 example

```json
{
  "createdAt": "2024-01-15T09:30:00Z",
  "id": "string",
  "key": "string",
  "keyPrefix": "string",
  "name": "string"
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
curl -X POST 'https://api.example.com/api/me/api-keys' \
  -H 'Authorization: Bearer <token>' \
  -H 'Content-Type: application/json' \
  -d '{
  "name": {}
}'
```

[PreviousChange my password](https://docs.umami.is/docs/api-reference/update-my-password) [NextDelete an API key](https://docs.umami.is/docs/api-reference/delete-my-api-key)

On this page