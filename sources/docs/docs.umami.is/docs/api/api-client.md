# Source: https://docs.umami.is/docs/api/api-client

Menu

Clients

# API client

Copy page

## Overview[#](https://docs.umami.is/docs/api/api-client#overview)

Umami API Client is built in TypeScript and contains functions to call every API endpoint available in Umami.

## Requirements[#](https://docs.umami.is/docs/api/api-client#requirements)

- [Node.js](https://nodejs.org/) version 18.18 or newer

## Installation[#](https://docs.umami.is/docs/api/api-client#installation)

```shell
npm install @umami/api-client
```

## Configure[#](https://docs.umami.is/docs/api/api-client#configure)

The following environment variables are required to call your own API.

```dotenv
UMAMI_API_CLIENT_USER_ID
UMAMI_API_CLIENT_SECRET
UMAMI_API_CLIENT_ENDPOINT
```

To access Umami Cloud, these environment variables are required.

```dotenv
UMAMI_API_KEY
UMAMI_API_CLIENT_ENDPOINT
```

More details on accessing Umami Cloud can be found under [API key](https://docs.umami.is/docs/cloud/api-key).

## Usage[#](https://docs.umami.is/docs/api/api-client#usage)

Import the configured api-client and query using the available class methods.

```js
import { getClient } from '@umami/api-client';

const client = getClient();

const { ok, data, status, error } = await client.getWebsites();
```

The result will come back in the following format.

```typescript
{
  ok: boolean;
  status: number;
  data?: T;
  error?: any;
}
```

## API Client function mapping[#](https://docs.umami.is/docs/api/api-client#api-client-function-mapping)

### Me[#](https://docs.umami.is/docs/api/api-client#me)

```text
getMe() ⇒ GET /me
updateMyPassword(data) ⇒ POST /me/password
getMyWebsites() ⇒ GET /me/websites
```

### Users[#](https://docs.umami.is/docs/api/api-client#users)

```text
getUsers() ⇒ GET /users
createUser(data) ⇒ POST /users
getUser(id) ⇒ GET /users/{id}
updateUser(id, data) ⇒ POST /users/{id}
deleteUser(id) ⇒ DEL /users/{id}
getUserWebsites(id) ⇒ GET /users/{id}/websites
getUserUsage(id, data) ⇒ GET /users/{id}/usage
```

### Teams[#](https://docs.umami.is/docs/api/api-client#teams)

```text
getTeams() ⇒ GET /teams
createTeam(data) ⇒ POST /teams
joinTeam(data) ⇒ POST /teams/join
getTeam(id) ⇒ GET /teams/{id}
updateTeam(id, data) ⇒ POST /teams/{id}
deleteTeam(id) ⇒ DEL /teams/{id}
getTeamUsers(id) ⇒ GET /teams/{id}/users
deleteTeamUser(teamId, userId) ⇒ DEL /teams/{teamId}/users/{userId}
getTeamWebsites(id) ⇒ GET /teams/{id}/websites
createTeamWebsites(id, data) ⇒ POST /teams/{id}/websites
deleteTeamWebsite(teamId, websiteId) ⇒ DEL /teams/{teamId}/websites/{websiteId}
```

### Websites[#](https://docs.umami.is/docs/api/api-client#websites)

```text
getWebsites() ⇒ GET /websites
createWebsite(data) ⇒ POST /websites
getWebsite(id) ⇒ GET /websites/{id}
updateWebsite(id, data) ⇒ POST /websites/{id}
deleteWebsite(id) ⇒ DEL /websites/{id}
getWebsiteActive(id) ⇒ GET /websites/{id}/active
getWebsiteEvents(id, data) ⇒ GET /websites/{id}/events
getWebsiteMetrics(id, data) ⇒ GET /websites/{id}/metrics
getWebsitePageviews(id, data) ⇒ GET /websites/{id}/pageviews
resetWebsite(id) ⇒ POST /websites/{id}/reset
getWebsiteStats(id, data) ⇒ GET /websites/{id}/stats
```

### Event Data[#](https://docs.umami.is/docs/api/api-client#event-data)

```text
getEventDataEvents(id, data) ⇒ GET /event-data/events
getEventDataFields(id, data) ⇒ GET /event-data/fields
getEventDataStats(id, data) ⇒ GET /event-data/stats
```

## Environment Variables[#](https://docs.umami.is/docs/api/api-client#environment-variables)

**UMAMI\_API\_CLIENT\_USER\_ID = <user uuid>**

The `USER_ID` of the User performing the API calls. Permission restrictions will apply based on application settings.

**UMAMI\_API\_CLIENT\_SECRET = <random string>**

A random string used to generate unique values. This needs to match the `APP_SECRET` used in the Umami application.

**UMAMI\_API\_CLIENT\_ENDPOINT = <API endpoint>**

The endpoint of your Umami API. Example: `https://{yourserver}/api/`

**UMAMI\_API\_KEY = <API Key string>**

A unique string provided by Umami Cloud.

[PreviousList website filter values](https://docs.umami.is/docs/api-reference/get-website-values) [NextNode Client](https://docs.umami.is/docs/api/node-client)

On this page