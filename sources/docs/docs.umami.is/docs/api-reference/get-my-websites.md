# Source: https://docs.umami.is/docs/api-reference/get-my-websites

Menu

Account

# List my websites

Copy page

GET`/api/me/websites`

Returns a paginated list of the current user's websites, optionally including websites accessible through team membership.

## Headers

| Name | Type | Description |
| --- | --- | --- |
| Authorizationrequired | string | Authentication credentials, e.g. `Bearer <token>`. |

## Query parameters

| Name | Type | Description |
| --- | --- | --- |
| page | integer | Page number, starting at 1. |
| pageSize | integer | Number of results per page. |
| maxResults | integer | Maximum number of results to include. |
| orderBy | string | Field to sort the results by. |
| sortDescending | enum<string> | Whether to sort results in descending order.
Options: `true`, `false`

 |
| includeTeams | string | Set a non-empty value to include websites accessible through team membership. |

## Responses

200The operation completed successfully.

| Name | Type | Description |
| --- | --- | --- |
| countrequired | number | Number of matching records. |
| datarequired | any\[\] | Data returned by the operation. |
| isCapped | boolean | Whether the results were truncated by the maximum result limit. |
| orderBy | string | Field to sort the results by. |
| pagerequired | number | Page number, starting at 1. |
| pageSizerequired | number | Number of results per page. |
| search | string | Search text used to filter results. |
| sortDescending | boolean | Whether to sort results in descending order. |

200 example

```json
{
  "count": 0,
  "data": [
    {
      "createdAt": "2024-01-15T09:30:00Z",
      "createdBy": "string",
      "deletedAt": "2024-01-15T09:30:00Z",
      "domain": "string",
      "id": "string",
      "name": "string",
      "recorderEnabled": true,
      "replayConfig": "string",
      "resetAt": "2024-01-15T09:30:00Z",
      "teamId": "string",
      "updatedAt": "2024-01-15T09:30:00Z",
      "userId": "string",
      "createUser": {
        "id": "string",
        "username": "string"
      },
      "shareId": "string",
      "team": {
        "members": [
          {
            "role": "string",
            "userId": "string"
          }
        ]
      },
      "user": {
        "id": "string",
        "username": "string"
      }
    }
  ],
  "isCapped": true,
  "orderBy": "string",
  "page": 0,
  "pageSize": 0,
  "search": "string",
  "sortDescending": true
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
curl -X GET 'https://api.example.com/api/me/websites' \
  -H 'Authorization: Bearer <token>'
```

[PreviousList my team memberships](https://docs.umami.is/docs/api-reference/get-my-teams) [NextGet a user's two-factor status](https://docs.umami.is/docs/api-reference/get-admin-users-user-id2fa)

On this page