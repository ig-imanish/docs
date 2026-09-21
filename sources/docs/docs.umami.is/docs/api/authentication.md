# Source: https://docs.umami.is/docs/api/authentication

Menu

API

# Authentication

Copy page

Self-hosted Umami supports two ways to authenticate API requests. **API keys** are the recommended method. Username and password authentication is still supported as an alternative.

For **Umami Cloud**, API keys are the only authentication method. See [API key](https://docs.umami.is/docs/cloud/api-key).

## API keys (recommended)[#](https://docs.umami.is/docs/api/authentication#api-keys-recommended)

API keys are long-lived credentials that are ideal for programmatic access. They don't expire and can be revoked individually.

### Create a key[#](https://docs.umami.is/docs/api/authentication#create-a-key)

Generate a key from the app by clicking your profile icon, selecting **Settings**, and navigating to **API keys**. Click **Create key** and save the value — it is only shown once.

You can also create, list, and delete keys programmatically:

- [Create an API key](https://docs.umami.is/docs/api-reference/create-my-api-key)
- [List my API keys](https://docs.umami.is/docs/api-reference/get-my-api-keys)
- [Delete an API key](https://docs.umami.is/docs/api-reference/delete-my-api-key)

### Using your key[#](https://docs.umami.is/docs/api/authentication#using-your-key)

Pass the key with an `Authorization` header using the Bearer authentication scheme.

request

```http
Authorization: Bearer <api-key>
```

For example, with `curl` it would look like this:

```shell
curl https://{yourserver}/api/websites \
   -H "Accept: application/json" \
   -H "Authorization: Bearer <api-key>"
```

## Username and password (alternative)[#](https://docs.umami.is/docs/api/authentication#username-and-password-alternative)

If you prefer, you can still authenticate by exchanging your username and password for a temporary token.

### POST /api/auth/login[#](https://docs.umami.is/docs/api/authentication#post-apiauthlogin)

First you need to get a _token_ in order to make API requests. You need to make a `POST` request to the `/api/auth/login` endpoint with the following data:

```json
{
  "username": "your-username",
  "password": "your-password"
}
```

If successful you should get a response like the following:

```json
{
  "token": "eyTMjU2IiwiY...4Q0JDLUhWxnIjoiUE_A",
  "user": {
    "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
    "username": "admin",
    "role": "admin",
    "createdAt": "2000-00-00T00:00:00.000Z",
    "isAdmin": true
  }
}
```

Save the token value and send an `Authorization` header with all your data requests with the value `Bearer <token>`. Your request header should look something like this:

request

```http
Authorization: Bearer eyTMjU2IiwiY...4Q0JDLUhWxnIjoiUE_A
```

For example, with `curl` it would look like this:

```shell
curl https://{yourserver}/api/websites \
   -H "Accept: application/json" \
   -H "Authorization: Bearer <token>"
```

The authorization token is expected with every API call that requires permissions.

### POST /api/auth/verify[#](https://docs.umami.is/docs/api/authentication#post-apiauthverify)

You can verify if the token is still valid.

**Sample response**

```json
{
  "id": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
  "username": "admin",
  "role": "admin",
  "createdAt": "2000-00-00T00:00:00.000Z",
  "isAdmin": true,
  "teams": []
}
```

[PreviousOverview](https://docs.umami.is/docs/api) [NextSending stats](https://docs.umami.is/docs/api/sending-stats)

On this page