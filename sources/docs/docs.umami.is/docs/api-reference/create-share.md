# Source: https://docs.umami.is/docs/api-reference/create-share

Menu

Shares

# Create a share

Copy page

POST`/api/share`

Creates a named share for a website, board, link, or pixel with parameters and an optional custom slug.

## Headers

| Name | Type | Description |
| --- | --- | --- |
| Authorizationrequired | string | Authentication credentials, e.g. `Bearer <token>`. |

## Request body

| Name | Type | Description |
| --- | --- | --- |
| entityIdrequired | string | ID of the resource being shared. |
| namerequired | string | Display name of the resource. |
| parametersrequired | object | Configuration parameters for the resource. |
| shareTyperequired | integer | Type of resource made available by the share. |
| slug | string | URL slug used to access the resource. |

Example request

```json
{
  "entityId": "123e4567-e89b-12d3-a456-426614174000",
  "name": "string",
  "parameters": null,
  "shareType": 0,
  "slug": "string"
}
```

## Responses

200The operation completed successfully.

| Name | Type | Description |
| --- | --- | --- |
| createdAtrequired | string | Date and time the record was created. |
| entityIdrequired | string | ID of the resource being shared. |
| idrequired | string | Unique identifier of the resource. |
| namerequired | string | Display name of the resource. |
| parametersrequired | anyOf | Configuration parameters for the resource. |
| 
Allowed types

 |
| shareTyperequired | number | Type of resource made available by the share. |
| slugrequired | string | URL slug used to access the resource. |
| updatedAtrequired | string | Date and time the record was last updated. |

200 example

```json
{
  "createdAt": "2024-01-15T09:30:00Z",
  "entityId": "string",
  "id": "string",
  "name": "string",
  "parameters": "string",
  "shareType": 0,
  "slug": "string",
  "updatedAt": "2024-01-15T09:30:00Z"
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
curl -X POST 'https://api.example.com/api/share' \
  -H 'Authorization: Bearer <token>' \
  -H 'Content-Type: application/json' \
  -d '{
  "entityId": "123e4567-e89b-12d3-a456-426614174000",
  "name": "string",
  "parameters": null,
  "shareType": 0,
  "slug": "string"
}'
```

[PreviousList a visitor's session replays](https://docs.umami.is/docs/api-reference/get-website-session-replays) [NextDelete a share](https://docs.umami.is/docs/api-reference/delete-share)

On this page