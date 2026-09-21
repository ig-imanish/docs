# Source: https://docs.umami.is/docs/enable-redis

Menu

Configuration

# Enable Redis

Copy page

Umami supports [Redis](https://redis.io/) as a caching layer for improved performance. When Redis is enabled, frequently accessed data such as website lookups and session information is cached, reducing database queries and improving response times.

Additionally, login authentication will be handled by Redis sessions instead of JWT tokens, providing server-side session management.

## When to use Redis[#](https://docs.umami.is/docs/enable-redis#when-to-use-redis)

Redis is recommended when:

- You have a high-traffic website and want to reduce database load.
- You are running multiple Umami instances and need shared session management.
- You want faster response times for API calls.

Redis is optional. Without it, Umami uses direct database lookups and JWT-based authentication, which work well for most use cases.

## Usage[#](https://docs.umami.is/docs/enable-redis#usage)

To enable Redis, add a connection string as an environment variable called `REDIS_URL`.

```dotenv
REDIS_URL=redis://username:password@your-redis-server:port
```

If your Redis instance uses TLS, use the `rediss://` protocol:

```dotenv
REDIS_URL=rediss://username:password@your-redis-server:port
```

### Docker Compose example[#](https://docs.umami.is/docs/enable-redis#docker-compose-example)

To add Redis to an existing Docker Compose setup, add a Redis service and set the `REDIS_URL` environment variable:

```yaml
redis:
  image: redis:8.4.0
  command: redis-server --requirepass ${REDIS_PASSWORD}
  restart: always

umami:
  environment:
    REDIS_URL: redis://:${REDIS_PASSWORD}@redis:6379
```

## Behavior[#](https://docs.umami.is/docs/enable-redis#behavior)

If Redis becomes unavailable, Umami will fall back to direct database lookups. No data will be lost, but response times may increase until Redis is restored.

[PreviousUse Google Tag Manager](https://docs.umami.is/docs/google-tag-manager) [NextTwo-factor authentication](https://docs.umami.is/docs/two-factor-authentication)

On this page