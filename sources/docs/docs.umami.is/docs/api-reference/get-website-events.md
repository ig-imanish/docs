# Source: https://docs.umami.is/docs/api-reference/get-website-events

Menu

Events

# List tracked events

Copy page

GET`/api/websites/{websiteId}/events`

Returns a page of pageviews and custom events in the date range, newest first. Supports filtering by event name and searching event details.

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
| page | integer | Page number, starting at 1. |
| pageSize | integer | Number of results per page. |
| maxResults | integer | Maximum number of results to include. |
| search | string | Search text used to filter results. |

## Responses

200A page of events.

| Name | Type | Description |
| --- | --- | --- |
| countrequired | integer | Number of matching records. |
| datarequired | WebsiteEvent\[\] | Data returned by the operation. |
| 
properties

 |
| isCapped | boolean | Whether the results were truncated by the maximum result limit. |
| pagerequired | integer | Page number, starting at 1. |
| pageSizerequired | integer | Number of results per page. |

200 example

```json
{
  "count": 0,
  "data": [
    {
      "createdAt": "2024-01-15T09:30:00Z",
      "distinctId": "string",
      "eventName": "string",
      "eventType": -9007199254740991,
      "hostname": "string",
      "id": "123e4567-e89b-12d3-a456-426614174000",
      "pageTitle": "string",
      "referrerDomain": "string",
      "sessionId": "123e4567-e89b-12d3-a456-426614174000",
      "urlPath": "string",
      "urlQuery": "string",
      "websiteId": "123e4567-e89b-12d3-a456-426614174000"
    }
  ],
  "isCapped": true,
  "page": 0,
  "pageSize": 0
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
curl -X GET 'https://api.example.com/api/websites/{websiteId}/events' \
  -H 'Authorization: Bearer <token>'
```

[PreviousList event property values](https://docs.umami.is/docs/api-reference/get-event-data-values) [NextGet custom event counts over time](https://docs.umami.is/docs/api-reference/get-website-event-series)

On this page