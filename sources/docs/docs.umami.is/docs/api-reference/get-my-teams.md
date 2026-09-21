# Source: https://docs.umami.is/docs/api-reference/get-my-teams

Menu

Account

# List my team memberships

Copy page

GET`/api/me/teams`

Returns a paginated list of teams the current user belongs to, with sorting options.

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

## Responses

200The operation completed successfully.

| Name | Type | Description |
| --- | --- | --- |
| countrequired | number | Number of matching records. |
| datarequired | object\[\] | Data returned by the operation. |
| 
properties

 |
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
      "accessCode": "string",
      "createdAt": "2024-01-15T09:30:00Z",
      "deletedAt": "2024-01-15T09:30:00Z",
      "id": "string",
      "logoUrl": "string",
      "name": "string",
      "twoFactorRequired": true,
      "updatedAt": "2024-01-15T09:30:00Z"
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
curl -X GET 'https://api.example.com/api/me/teams' \
  -H 'Authorization: Bearer <token>'
```

[PreviousList my API keys](https://docs.umami.is/docs/api-reference/get-my-api-keys) [NextList my websites](https://docs.umami.is/docs/api-reference/get-my-websites)

On this page