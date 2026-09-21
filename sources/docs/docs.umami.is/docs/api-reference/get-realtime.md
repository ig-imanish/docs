# Source: https://docs.umami.is/docs/api-reference/get-realtime

Menu

Realtime

# Get real-time website activity

Copy page

GET`/api/realtime/{websiteId}`

Returns recent website activity and visitor data for the real-time view, applying the supplied filters.

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
| timezone | string | IANA time zone used to interpret dates and group results, for example America/New\_York. |
| unit | string | Time interval used to group results: minute, hour, day, month, or year. |
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
| countriesrequired | object | |
| eventsrequired | object\[\] | |
| 
properties

 |
| referrersrequired | object | |
| seriesrequired | object | |
| 

properties

 |
| timestamprequired | number | |
| totalsrequired | object | |
| 

properties

 |
| urlsrequired | object | |

200 example

```json
{
  "countries": {},
  "events": [
    {
      "__type": {},
      "browser": "string",
      "country": "string",
      "createdAt": "string",
      "device": "string",
      "eventName": "string",
      "hostname": "string",
      "os": "string",
      "referrerDomain": "string",
      "sessionId": "string",
      "urlPath": "string"
    }
  ],
  "referrers": {},
  "series": {
    "views": [
      {
        "t": "string",
        "x": "string",
        "y": 0
      }
    ],
    "visitors": [
      {
        "t": "string",
        "x": "string",
        "y": 0
      }
    ]
  },
  "timestamp": 0,
  "totals": {
    "countries": 0,
    "events": 0,
    "views": 0,
    "visitors": 0
  },
  "urls": {}
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
curl -X GET 'https://api.example.com/api/realtime/{websiteId}' \
  -H 'Authorization: Bearer <token>'
```

[PreviousGet website retention](https://docs.umami.is/docs/api-reference/get-website-retention) [NextGet website revenue over time](https://docs.umami.is/docs/api-reference/get-website-revenue-chart)

On this page