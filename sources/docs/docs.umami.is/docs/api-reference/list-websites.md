# Source: https://docs.umami.is/docs/api-reference/list-websites

Menu

Websites

# List websites

Copy page

GET`/api/websites`

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
| search | string | Search text used to filter results. |
| orderBy | string | Field to sort the results by. |
| sortDescending | enum<string> | Whether to sort results in descending order.
Options: `true`, `false`

 |
| includeTeams | string | When present, include websites accessible through owned or managed teams. |

## Responses

200A page of websites.

| Name | Type | Description |
| --- | --- | --- |
| countrequired | integer | Number of matching records. |
| datarequired | Website\[\] | Data returned by the operation. |
| 
properties

 |
| orderBy | string | Field to sort the results by. |
| pagerequired | integer | Page number, starting at 1. |
| pageSizerequired | integer | Number of results per page. |
| search | string | Search text used to filter results. |

200 example

```json
{
  "count": 0,
  "data": [
    {
      "createdAt": "2024-01-15T09:30:00Z",
      "createdBy": "123e4567-e89b-12d3-a456-426614174000",
      "deletedAt": "2024-01-15T09:30:00Z",
      "domain": "string",
      "id": "123e4567-e89b-12d3-a456-426614174000",
      "name": "string",
      "recorderEnabled": true,
      "replayConfig": {
        "blockSelector": "string",
        "heatmapEnabled": true,
        "heatmapSampleRate": 0,
        "maskLevel": "strict",
        "maxDuration": 0,
        "replayEnabled": true,
        "sampleRate": 0
      },
      "resetAt": "2024-01-15T09:30:00Z",
      "shareId": "string",
      "teamId": "123e4567-e89b-12d3-a456-426614174000",
      "updatedAt": "2024-01-15T09:30:00Z",
      "user": {
        "id": "123e4567-e89b-12d3-a456-426614174000",
        "username": "string"
      },
      "userId": "123e4567-e89b-12d3-a456-426614174000"
    }
  ],
  "orderBy": "string",
  "page": 0,
  "pageSize": 0,
  "search": "string"
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
curl -X GET 'https://api.example.com/api/websites' \
  -H 'Authorization: Bearer <token>'
```

[PreviousGet website utm metrics](https://docs.umami.is/docs/api-reference/get-website-utm-metrics) [NextCreate a website](https://docs.umami.is/docs/api-reference/create-website)

On this page