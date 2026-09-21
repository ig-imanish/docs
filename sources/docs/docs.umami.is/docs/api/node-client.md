# Source: https://docs.umami.is/docs/api/node-client

Menu

Clients

# Node Client

Copy page

## Overview[#](https://docs.umami.is/docs/api/node-client#overview)

The Umami node client allows you to send data to Umami on the server side.

## Installation[#](https://docs.umami.is/docs/api/node-client#installation)

```shell
npm install @umami/node
```

## Usage[#](https://docs.umami.is/docs/api/node-client#usage)

```js
import umami from '@umami/node';

umami.init({
  websiteId: '50429a93-8479-4073-be80-d5d29c09c2ec', // Your website id
  hostUrl: 'https://umami.mywebsite.com', // URL to your Umami instance
});

umami.track({ url: '/home' });
```

If using Umami Cloud, you can use `https://cloud.umami.is` as the host URL.

The properties you can send using the `.track` function are:

- **hostname**: Hostname of server
- **language**: Client language (eg. en-US)
- **referrer**: Page referrer
- **screen**: Screen dimensions (eg. 1920x1080)
- **title**: Page title
- **url**: Page url
- **name**: Event name (for custom events)
- **data**: Event data properties

[PreviousAPI client](https://docs.umami.is/docs/api/api-client) [NextOverview](https://docs.umami.is/docs/cloud)

On this page