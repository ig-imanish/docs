# Source: https://docs.umami.is/docs/api-reference/get-website-values

Menu

Websites

# List website filter values

Copy page

GET`/api/websites/{websiteId}/values`

Returns available values for a website filter, including saved segments or cohorts when requested, to populate filter choices.

## Headers

| Name | Type | Description |
| --- | --- | --- |
| Authorizationrequired | string | Authentication credentials, e.g. `Bearer <token>`. |

## Path parameters

| Name | Type | Description |
| --- | --- | --- |
| websiteIdrequired | string | ID of the website. |

## Query parameters

| Name | Type | Description |
| --- | --- | --- |
| startAt | number | Start of the date range as a Unix timestamp in milliseconds. |
| endAt | number | End of the date range as a Unix timestamp in milliseconds. |
| startDate | string | Start of the date range as an ISO 8601 date or date-time. |
| endDate | string | End of the date range as an ISO 8601 date or date-time. |
| timezone | string | IANA time zone used to interpret dates and group results, for example America/New\_York. |
| unit | string | Time interval used to group results: minute, hour, day, month, or year. |
| compare | enum<string> | Comparison period: prev for the previous period or yoy for the same period last year.
Options: `prev`, `yoy`

 |
| typerequired | string | Type of resource or analytics dimension to return. |
| search | string | Search text used to filter results. |

## Responses

200The operation completed successfully.

| Name | Type | Description |
| --- | --- | --- |
| any\[\] | any\[\] | |

200 example

```json
[
  {}
]
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
curl -X GET 'https://api.example.com/api/websites/{websiteId}/values?type=string' \
  -H 'Authorization: Bearer <token>'
```

[PreviousTransfer website ownership](https://docs.umami.is/docs/api-reference/transfer-website) [NextAPI client](https://docs.umami.is/docs/api/api-client)

On this page