# Source: https://docs.umami.is/docs/api-reference/get-website-event-series

Menu

Events

# Get custom event counts over time

Copy page

GET`/api/websites/{websiteId}/events/series`

Returns counts grouped by event name and time interval, optionally limited to the most frequent event names.

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
| startAtrequired | integer | Start of the date range as a Unix timestamp in milliseconds. |
| endAtrequired | integer | End of the date range as a Unix timestamp in milliseconds. |
| unit | string | Time interval used to group results: minute, hour, day, month, or year. |
| timezonerequired | string | IANA time zone used to interpret dates and group results, for example America/New\_York. |
| limit | number | Maximum number of rows to return. |
| path | string | Filter by page URL path. |
| referrer | string | Filter by referring URL. |
| title | string | Filter by page title. |
| query | string | Filter by page URL query string. |
| os | string | Operating system used by the visitor. |
| browser | string | Browser used by the visitor. |
| device | string | Device category used by the visitor. |
| country | string | Country code of the visitor. |
| region | string | Region or subdivision of the visitor. |
| city | string | City of the visitor. |
| tag | string | Tag attached to the tracked activity. |
| hostname | string | Hostname on which the activity occurred. |
| distinctId | string | Custom identifier assigned to the visitor. |
| language | string | Preferred language reported by the visitor browser. |
| event | string | Filter by custom event name. |
| utmSource | string | UTM campaign source. |
| utmMedium | string | UTM campaign medium. |
| utmCampaign | string | UTM campaign name. |
| utmContent | string | UTM campaign content. |
| utmTerm | string | UTM campaign search term. |
| excludeBounce | string | Set a non-empty value to exclude visits with only one pageview. |
| segment | string | ID of a saved segment used to filter results. |
| cohort | string | ID of a saved cohort used to filter visitors. |
| eventType | integer | Event type: 1 for a pageview or 2 for a custom event. |
| match | enum<string> | Whether records must match all filters or any filter.
Options: `all`, `any`

 |

## Responses

200The operation completed successfully.

| Name | Type | Description |
| --- | --- | --- |
| trequired | string | |
| xrequired | string | |
| yrequired | number | |

200 example

```json
[
  {
    "t": "string",
    "x": "string",
    "y": 0
  }
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
curl -X GET 'https://api.example.com/api/websites/{websiteId}/events/series?startAt=0&endAt=0&timezone=string' \
  -H 'Authorization: Bearer <token>'
```

[PreviousList tracked events](https://docs.umami.is/docs/api-reference/get-website-events) [NextGet website event statistics](https://docs.umami.is/docs/api-reference/get-website-event-stats)

On this page