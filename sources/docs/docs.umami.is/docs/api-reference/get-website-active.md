# Source: https://docs.umami.is/docs/api-reference/get-website-active

Menu

Stats

# Get active website visitors

Copy page

GET`/api/websites/{websiteId}/active`

Returns the number of visitors active on the website in the last few minutes.

## Headers

| Name | Type | Description |
| --- | --- | --- |
| Authorizationrequired | string | Authentication credentials, e.g. `Bearer <token>`. |

## Path parameters

| Name | Type | Description |
| --- | --- | --- |
| websiteIdrequired | string | Website ID. |

## Responses

200Active visitor count.

| Name | Type | Description |
| --- | --- | --- |
| visitorsrequired | integer | Unique visitor counts for the selected period. |

200 example

```json
{
  "visitors": 0
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
curl -X GET 'https://api.example.com/api/websites/{websiteId}/active' \
  -H 'Authorization: Bearer <token>'
```

[PreviousUpdate a share](https://docs.umami.is/docs/api-reference/update-share) [NextGet ranked website metrics](https://docs.umami.is/docs/api-reference/get-website-metrics)

On this page