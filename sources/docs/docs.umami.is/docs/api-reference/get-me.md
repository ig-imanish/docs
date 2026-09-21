# Source: https://docs.umami.is/docs/api-reference/get-me

Menu

Account

# Get my authentication details

Copy page

GET`/api/me`

Returns the current authentication context, including the authenticated user or share credentials.

## Headers

| Name | Type | Description |
| --- | --- | --- |
| Authorizationrequired | string | Authentication credentials, e.g. `Bearer <token>`. |

## Responses

200The operation completed successfully.

| Name | Type | Description |
| --- | --- | --- |
| apiKey | object | API key authentication details. |
| 
properties

 |
| authType | anyOf | |
| 

Allowed types

 |
| shareToken | object | |
| 

properties

 |
| user | object | User associated with the resource. |
| 

properties

 |

200 example

```json
{
  "apiKey": {
    "id": "string",
    "name": "string"
  },
  "authType": {},
  "shareToken": {
    "boardId": "string",
    "linkId": "string",
    "linkIds": [
      "string"
    ],
    "parameters": {
      "allowFilter": true,
      "theme": {}
    },
    "pixelId": "string",
    "pixelIds": [
      "string"
    ],
    "shareType": 0,
    "websiteId": "string",
    "websiteIds": [
      "string"
    ]
  },
  "user": {
    "id": "string",
    "isAdmin": true,
    "role": "string",
    "username": "string"
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
curl -X GET 'https://api.example.com/api/me' \
  -H 'Authorization: Bearer <token>'
```

[PreviousDelete an API key](https://docs.umami.is/docs/api-reference/delete-my-api-key) [NextList my API keys](https://docs.umami.is/docs/api-reference/get-my-api-keys)

On this page