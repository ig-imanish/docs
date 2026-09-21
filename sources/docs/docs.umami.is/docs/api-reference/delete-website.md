# Source: https://docs.umami.is/docs/api-reference/delete-website

Menu

Websites

# Delete a website

Copy page

DELETE`/api/websites/{websiteId}`

Deletes the specified website after checking the caller's permission to remove it.

## Headers

| Name | Type | Description |
| --- | --- | --- |
| Authorizationrequired | string | Authentication credentials, e.g. `Bearer <token>`. |

## Path parameters

| Name | Type | Description |
| --- | --- | --- |
| websiteIdrequired | string | Website ID. |

## Responses

200Website deleted.

| Name | Type | Description |
| --- | --- | --- |
| okrequired | boolean | Whether the operation succeeded. |

200 example

```json
{
  "ok": true
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
curl -X DELETE 'https://api.example.com/api/websites/{websiteId}' \
  -H 'Authorization: Bearer <token>'
```

[PreviousUpdate a website](https://docs.umami.is/docs/api-reference/update-website) [NextGet visitor charts for websites](https://docs.umami.is/docs/api-reference/get-websites-charts)

On this page