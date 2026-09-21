# Source: https://docs.umami.is/docs/api-reference/get-website-stats

Menu

Stats

# Get website summary statistics

Copy page

GET`/api/websites/{websiteId}/stats`

Returns pageviews, unique visitors, visits, bounces, and total time on site for the selected date range and comparison period.

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

200Summary stats with comparison.

| Name | Type | Description |
| --- | --- | --- |
| bouncesrequired | number | Number of visits with only one pageview. |
| comparisonrequired | object | |
| 
properties

 |
| pageviewsrequired | number | Pageview counts for the selected period. |
| totaltimerequired | number | Total visit duration in seconds. |
| visitorsrequired | number | Unique visitor counts for the selected period. |
| visitsrequired | number | Visit counts for the selected period. |

200 example

```json
{
  "bounces": 0,
  "comparison": {
    "bounces": 0,
    "pageviews": 0,
    "totaltime": 0,
    "visitors": 0,
    "visits": 0
  },
  "pageviews": 0,
  "totaltime": 0,
  "visitors": 0,
  "visits": 0
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
curl -X GET 'https://api.example.com/api/websites/{websiteId}/stats' \
  -H 'Authorization: Bearer <token>'
```

[PreviousGet pageviews and sessions over time](https://docs.umami.is/docs/api-reference/get-website-pageviews) [NextGet detailed website metrics](https://docs.umami.is/docs/api-reference/get-website-expanded-metrics)

On this page