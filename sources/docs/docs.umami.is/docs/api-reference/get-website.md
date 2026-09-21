# Source: https://docs.umami.is/docs/api-reference/get-website

Menu

Websites

# Get a website

Copy page

GET`/api/websites/{websiteId}`

Returns the specified website's details and configuration.

## Headers

| Name | Type | Description |
| --- | --- | --- |
| Authorizationrequired | string | Authentication credentials, e.g. `Bearer <token>`. |

## Path parameters

| Name | Type | Description |
| --- | --- | --- |
| websiteIdrequired | string | Website ID. |

## Responses

200Website details, or null if it does not exist.

| Name | Type | Description |
| --- | --- | --- |
| anyOf | anyOf | |
| 
Allowed types

 |

200 example

```json
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
curl -X GET 'https://api.example.com/api/websites/{websiteId}' \
  -H 'Authorization: Bearer <token>'
```

[PreviousCreate a website](https://docs.umami.is/docs/api-reference/create-website) [NextUpdate a website](https://docs.umami.is/docs/api-reference/update-website)

On this page