# Source: https://docs.umami.is/docs/api-reference/get-website-pageviews

Menu

Stats

# Get pageviews and sessions over time

Copy page

GET`/api/websites/{websiteId}/pageviews`

Returns pageviews and sessions grouped by the requested time interval and timezone, including a comparison period when requested.

## Headers

| Name | Type | Description |
| --- | --- | --- |
| Authorizationrequired | string | Authentication credentials, e.g. `Bearer <token>`. |

## Path parameters

| Name | Type | Description |
| --- | --- | --- |
| websiteIdrequired | string | Website ID. |

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
| segment | string | ID of a saved segment used to filter results. |
| cohort | string | ID of a saved cohort used to filter visitors. |
| eventType | integer | Event type: 1 for a pageview or 2 for a custom event. |
| excludeBounce | string | Set a non-empty value to exclude visits with only one pageview. |
| match | enum<string> | Whether records must match all filters or any filter.

Options: `all`, `any`

 |

## Responses

200Time series.

| Name | Type | Description |
| --- | --- | --- |
| compare | object | Present when \`compare\` was requested. |
| 
properties

 |
| endDate | string | End of the date range as an ISO 8601 date or date-time. |
| pageviewsrequired | TimeSeriesPoint\[\] | Pageview counts for the selected period. |
| 

properties

 |
| sessionsrequired | TimeSeriesPoint\[\] | |
| 

properties

 |
| startDate | string | Start of the date range as an ISO 8601 date or date-time. |

200 example

```json
{
  "compare": {
    "endDate": "2024-01-15T09:30:00Z",
    "pageviews": [
      {
        "x": "string",
        "y": 0
      }
    ],
    "sessions": [
      {
        "x": "string",
        "y": 0
      }
    ],
    "startDate": "2024-01-15T09:30:00Z"
  },
  "endDate": "2024-01-15T09:30:00Z",
  "pageviews": [
    {
      "x": "string",
      "y": 0
    }
  ],
  "sessions": [
    {
      "x": "string",
      "y": 0
    }
  ],
  "startDate": "2024-01-15T09:30:00Z"
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
curl -X GET 'https://api.example.com/api/websites/{websiteId}/pageviews' \
  -H 'Authorization: Bearer <token>'
```

[PreviousGet ranked website metrics](https://docs.umami.is/docs/api-reference/get-website-metrics) [NextGet website summary statistics](https://docs.umami.is/docs/api-reference/get-website-stats)

On this page