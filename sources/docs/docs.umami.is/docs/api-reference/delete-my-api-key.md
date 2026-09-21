# Source: https://docs.umami.is/docs/api-reference/delete-my-api-key

Menu

Account

# Delete an API key

Copy page

DELETE`/api/me/api-keys/{keyId}`

Deletes an API key belonging to the current user, revoking its access. Available on self-hosted installations.

## Headers

| Name | Type | Description |
| --- | --- | --- |
| Authorizationrequired | string | Authentication credentials, e.g. `Bearer <token>`. |

## Path parameters

| Name | Type | Description |
| --- | --- | --- |
| keyIdrequired | string | ID of the API key. |

## Responses

200The operation completed successfully.

| Name | Type | Description |
| --- | --- | --- |
| okrequired | any | Whether the operation succeeded. |

200 example

```json
{
  "ok": {}
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
curl -X DELETE 'https://api.example.com/api/me/api-keys/{keyId}' \
  -H 'Authorization: Bearer <token>'
```

[PreviousCreate an API key](https://docs.umami.is/docs/api-reference/create-my-api-key) [NextGet my authentication details](https://docs.umami.is/docs/api-reference/get-me)

On this page