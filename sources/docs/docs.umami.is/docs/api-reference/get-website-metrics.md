# Source: https://docs.umami.is/docs/api-reference/get-website-metrics

Menu

Stats

# Get ranked website metrics

Copy page

GET`/api/websites/{websiteId}/metrics`

Returns the most frequent values for a dimension such as pages, referrers, countries, browsers, campaigns, or events. Counts pageviews or events for activity dimensions and unique visitors for visitor dimensions.

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
| typerequired | string | Dimension to rank: path, entry, exit, title, query, hostname, referrer, domain, channel, event, tag, browser, os, device, screen, language, country, region, city, distinctId, utmSource, utmMedium, utmCampaign, utmContent, utmTerm. |
| limit | number | Maximum number of rows to return. |
| offset | number | Number of rows to skip before returning results. |
| search | string | Search text used to filter results. |
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

200Ranked rows.

| Name | Type | Description |
| --- | --- | --- |
| t | string | |
| xrequired | string | null | Dimension value (e.g. a path or country). |
| yrequired | number | Count of views/events or unique visitors. |

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
curl -X GET 'https://api.example.com/api/websites/{websiteId}/metrics?type=string' \
  -H 'Authorization: Bearer <token>'
```

[PreviousGet active website visitors](https://docs.umami.is/docs/api-reference/get-website-active) [NextGet pageviews and sessions over time](https://docs.umami.is/docs/api-reference/get-website-pageviews)

On this page