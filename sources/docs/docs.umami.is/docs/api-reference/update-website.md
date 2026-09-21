# Source: https://docs.umami.is/docs/api-reference/update-website

Menu

Websites

# Update a website

Copy page

POST`/api/websites/{websiteId}`

Updates a website's name, domain, sharing settings, or recording configuration.

## Headers

| Name | Type | Description |
| --- | --- | --- |
| Authorizationrequired | string | Authentication credentials, e.g. `Bearer <token>`. |

## Path parameters

| Name | Type | Description |
| --- | --- | --- |
| websiteIdrequired | string | Website ID. |

## Request body

| Name | Type | Description |
| --- | --- | --- |
| domain | string | Domain name associated with the resource. |
| name | string | Display name of the resource. |
| replayConfig | anyOf | Session replay and heatmap recording configuration. |
| 
Allowed types

 |
| shareId | string | null | Identifier used to access a shared resource. |

Example request

```json
{
  "domain": "string",
  "name": "string",
  "replayConfig": {
    "blockSelector": "string",
    "heatmapEnabled": true,
    "heatmapSampleRate": 0,
    "maskLevel": "strict",
    "maxDuration": 0,
    "replayEnabled": true,
    "sampleRate": 0
  },
  "shareId": "string"
}
```

## Responses

200Website updated.

| Name | Type | Description |
| --- | --- | --- |
| createdAtrequired | string | null | Date and time the record was created. |
| createdByrequired | string | null | ID of the user who created the resource. |
| deletedAtrequired | string | null | Date and time the record was deleted, if applicable. |
| domainrequired | string | null | Domain name associated with the resource. |
| idrequired | string | Unique identifier of the resource. |
| namerequired | string | Display name of the resource. |
| recorderEnabledrequired | boolean | Whether recording is enabled for the website. |
| replayConfigrequired | anyOf | Session replay and heatmap recording configuration. |
| 
Allowed types

 |
| resetAtrequired | string | null | Date and time the website analytics were last reset. |
| shareIdrequired | string | null | Identifier used to access a shared resource. |
| teamIdrequired | string | null | ID of the associated team. |
| updatedAtrequired | string | null | Date and time the record was last updated. |
| user | object | |
| 

properties

 |
| userIdrequired | string | null | ID of the associated user. |

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

500Server error.

| Name | Type | Description |
| --- | --- | --- |
| errorrequired | object | Error details returned when the operation fails. |
| 
properties

 |

500 example

```json
{
  "error": {
    "code": "server-error",
    "message": "Server error.",
    "status": 500
  }
}
```

## Code samples

cURLJavaScriptPython

cURL

```bash
curl -X POST 'https://api.example.com/api/websites/{websiteId}' \
  -H 'Authorization: Bearer <token>' \
  -H 'Content-Type: application/json' \
  -d '{
  "domain": "string",
  "name": "string",
  "replayConfig": {
    "blockSelector": "string",
    "heatmapEnabled": true,
    "heatmapSampleRate": 0,
    "maskLevel": "strict",
    "maxDuration": 0,
    "replayEnabled": true,
    "sampleRate": 0
  },
  "shareId": "string"
}'
```

[PreviousGet a website](https://docs.umami.is/docs/api-reference/get-website) [NextDelete a website](https://docs.umami.is/docs/api-reference/delete-website)

On this page