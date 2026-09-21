# Source: https://docs.umami.is/docs/environment-variables

Menu

Configuration

# Environment variables

Copy page

You can configure Umami with the use of environment variables. They go into the same `.env` file as your `DATABASE_URL`.

---

## Runtime variables[#](https://docs.umami.is/docs/environment-variables#runtime-variables)

Runtime variables are recognized when Umami is running. You can set your environment variables prior to starting the application.

### APP\_SECRET[#](https://docs.umami.is/docs/environment-variables#app_secret)

v1.0.0

A random string used to secure authentication tokens. Each installation should have a unique value. You can generate one with:

```shell
openssl rand -hex 32
```

```
APP_SECRET = "random string"
```

### CLIENT\_IP\_HEADER[#](https://docs.umami.is/docs/environment-variables#client_ip_header)

v1.24.0

HTTP header to check for the client's IP address. This is useful when you're behind a proxy that uses non-standard headers.

```
CLIENT_IP_HEADER = "header name"
```

### COLLECT\_API\_ENDPOINT[#](https://docs.umami.is/docs/environment-variables#collect_api_endpoint)

v1.34.0

Allows you to send metrics to a location different than the default `/api/send`. This is to help you avoid some [ad blockers](https://docs.umami.is/docs/bypass-ad-blockers).

```
COLLECT_API_ENDPOINT = "/my-custom-route"
```

### CORS\_MAX\_AGE[#](https://docs.umami.is/docs/environment-variables#cors_max_age)

v2.0.0

How many seconds a CORS preflight should last. Default is 24 hours.

```
CORS_MAX_AGE = 86400
```

### DATABASE\_URL[#](https://docs.umami.is/docs/environment-variables#database_url)

v1.0.0

```
DATABASE_URL = "connection string"
```

Connection string for your database. This is the only required variable.

### DEBUG[#](https://docs.umami.is/docs/environment-variables#debug)

v2.0.0

Console logging for specific areas of the application. Values include `umami:auth`, `umami:clickhouse`, `umami:kafka`, `umami:middleware`, and `umami:prisma`.

```
DEBUG = "umami:*"
```

### DISABLE\_BOT\_CHECK[#](https://docs.umami.is/docs/environment-variables#disable_bot_check)

v2.0.0

By default bots are excluded from statistics. This disables checking for bots.

```
DISABLE_BOT_CHECK = 1
```

### DISABLE\_LOGIN[#](https://docs.umami.is/docs/environment-variables#disable_login)

v1.26.0

Disables the login page for the application.

```
DISABLE_LOGIN = 1
```

### DISABLE\_TELEMETRY[#](https://docs.umami.is/docs/environment-variables#disable_telemetry)

v2.0.0

Umami collects completely anonymous telemetry data in order help improve the application. You can choose to disable this if you don't want to participate.

```
DISABLE_TELEMETRY = 1
```

### DISABLE\_UPDATES[#](https://docs.umami.is/docs/environment-variables#disable_updates)

v1.33.0

Disables the check for new versions of Umami.

```
DISABLE_UPDATES = 1
```

### ENABLE\_TEST\_CONSOLE[#](https://docs.umami.is/docs/environment-variables#enable_test_console)

v2.0.0

Enables the internal test page, `{host}/console`. Admin access is required. Users can manually fire pageviews and events to their websites.

```
ENABLE_TEST_CONSOLE = 1
```

### FAVICON\_URL[#](https://docs.umami.is/docs/environment-variables#favicon_url)

v2.18.0

The URL of the service for displaying website icons.

```
FAVICON_URL = "service URL"
```

The default is `icons.duckduckgo.com`:

- [https://icons.duckduckgo.com/ip3/{{domain}}.ico](https://icons.duckduckgo.com/ip3/%7B%7Bdomain%7D%7D.ico)

Some alternatives you can use:

- [https://www.google.com/s2/favicons?domain={{domain}}](https://www.google.com/s2/favicons?domain=%7B%7Bdomain%7D%7D)
- [https://logo.clearbit.com/{{domain}}](https://logo.clearbit.com/%7B%7Bdomain%7D%7D)

### GEO\_DATABASE\_URL[#](https://docs.umami.is/docs/environment-variables#geo_database_url)

v2.0.0

The URL for downloading a MaxMind-compatible GeoIP database in MMDB format. This is used for IP-based location detection when location headers from a CDN are not available.

```
GEO_DATABASE_URL = "https://example.com/GeoLite2-City.mmdb"
```

### HOSTNAME / PORT[#](https://docs.umami.is/docs/environment-variables#hostname--port)

v1.0.0

If you are running on an environment which requires you to bind to a specific hostname or port, such as Heroku, you can add these variables and start your app with `npm run start-env` instead of `npm start`.

```
HOSTNAME = "my.hostname.com"
PORT = 3000
```

### IGNORE\_IP[#](https://docs.umami.is/docs/environment-variables#ignore_ip)

v1.0.0

You can provide a comma-delimited list of IP addresses and CIDR ranges to exclude from data collection.

```
IGNORE_IP = "192.168.0.1, 10.0.0.0/24, 2001:db8::/32"
```

### LOG\_QUERY[#](https://docs.umami.is/docs/environment-variables#log_query)

v2.0.0

If you are running in development mode, this will log database queries to the console for debugging.

```
LOG_QUERY = 1
```

### PRIVATE\_MODE[#](https://docs.umami.is/docs/environment-variables#private_mode)

v2.11.0

Disables all external network calls. Note, this will also disable all website icons since they come from duckduckgo.com.

```
PRIVATE_MODE = 1
```

### REDIS\_URL[#](https://docs.umami.is/docs/environment-variables#redis_url)

v3.0.1

Optional Redis connection string used for caching and coordination features. If omitted, Redis-backed features stay disabled.

```
REDIS_URL = "redis://localhost:6379"
```

### REMOVE\_TRAILING\_SLASH[#](https://docs.umami.is/docs/environment-variables#remove_trailing_slash)

v1.26.0

Removes the trailing slash from all incoming urls.

```
REMOVE_TRAILING_SLASH = 1
```

### SALT\_ROTATION[#](https://docs.umami.is/docs/environment-variables#salt_rotation)

v3.1.0

Controls how often the anonymous session salt rotates for generated session identifiers. The default is `month`.

```
SALT_ROTATION = "month"
```

### SKIP\_LOCATION\_HEADERS[#](https://docs.umami.is/docs/environment-variables#skip_location_headers)

v2.15.0

Skips using known location headers for country/region/city detection and forces using the local geo database.

This is useful in environments where only the country (without region or city) header is set from the proxy or CDN (like Cloudflare’s `CF-IPCountry` when Network > IP Geolocation is switched to On).

```
SKIP_LOCATION_HEADERS = 1
```

### TRACKER\_SCRIPT\_NAME[#](https://docs.umami.is/docs/environment-variables#tracker_script_name)

v1.26.0

Allows you to assign a custom name to the tracker script different from the default `script.js`. This is to help you avoid some [ad blockers](https://docs.umami.is/docs/bypass-ad-blockers).

The `.js` extension is not required. The value can also be any path you choose, for example `/path/to/tracker`.

```
TRACKER_SCRIPT_NAME = "custom-script-name.js"
```

### TWO\_FACTOR\_ENCRYPTION\_KEY[#](https://docs.umami.is/docs/environment-variables#two_factor_encryption_key)

v3.3.0

A 64-character hex string (256-bit key) used to encrypt [two-factor authentication](https://docs.umami.is/docs/two-factor-authentication) secrets. Required before any user can enable 2FA. You can generate one with:

```shell
openssl rand -hex 32
```

```
TWO_FACTOR_ENCRYPTION_KEY = "random hex string"
```

### USE\_UUIDV7[#](https://docs.umami.is/docs/environment-variables#use_uuidv7)

v3.0.2

Uses UUIDv7 instead of UUIDv4 for generated random identifiers. Deterministic IDs derived from analytics data are unchanged.

```
USE_UUIDV7 = 1
```

---

## Build time variables[#](https://docs.umami.is/docs/environment-variables#build-time-variables)

Build time variables are only recognized during the build process. This also includes building custom Docker images. You need to set your environment variables prior to building the application.

### ALLOWED\_FRAME\_URLS[#](https://docs.umami.is/docs/environment-variables#allowed_frame_urls)

v2.3.0

A space-delimited list of urls allowed to host the application in an iframe.

```
ALLOWED_FRAME_URLS = "URLs"
```

### BASE\_PATH[#](https://docs.umami.is/docs/environment-variables#base_path)

v1.9.0

If you want to host Umami under a subdirectory. You may need to update your reverse proxy settings to correctly handle the BASE\_PATH prefix.

```
BASE_PATH = "/custom"
```

### BUILD\_GEO[#](https://docs.umami.is/docs/environment-variables#build_geo)

v3.0.0

Run the local GeoIP database setup step even in Vercel environment.

```
BUILD_GEO = 1
```

### DATABASE\_TYPE[#](https://docs.umami.is/docs/environment-variables#database_type)

v2.0.0

```
DATABASE_TYPE = "postgresql"
```

The type of DB to be used. This is only required for the Docker build.

### DEFAULT\_CURRENCY / DEFAULT\_LOCALE[#](https://docs.umami.is/docs/environment-variables#default_currency--default_locale)

v3.1.0

Sets the default currency and locale used by the application UI before a user chooses their own preferences.

```
DEFAULT_CURRENCY = "USD"
DEFAULT_LOCALE = "en-US"
```

### DIRECT\_DATABASE\_URL[#](https://docs.umami.is/docs/environment-variables#direct_database_url)

v3.2.0

Direct PostgreSQL connection string used for Prisma migrations during `check-db`. This is useful when `DATABASE_URL` points to a pooled connection that should not be used for migration commands.

```
DIRECT_DATABASE_URL = "connection string"
```

### FORCE\_SSL[#](https://docs.umami.is/docs/environment-variables#force_ssl)

v1.0.0

This will send a HTTP `Strict-Transport-Security` response header with all requests. See [https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Strict-Transport-Security](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Strict-Transport-Security).

```
FORCE_SSL = 1
```

### SKIP\_BUILD\_GEO[#](https://docs.umami.is/docs/environment-variables#skip_build_geo)

v3.1.0

Skips the local GeoIP database setup step in the build process.

```
SKIP_BUILD_GEO = 1
```

### SKIP\_DB\_CHECK[#](https://docs.umami.is/docs/environment-variables#skip_db_check)

v2.0.0

Skips the `check-db` step in the build process. Used for Docker builds.

```
SKIP_DB_CHECK = 1
```

### SKIP\_DB\_MIGRATION[#](https://docs.umami.is/docs/environment-variables#skip_db_migration)

v2.0.0

Skips the Prisma migration step in the build process. Setting `SKIP_DB_CHECK` also skips this step.

```
SKIP_DB_MIGRATION = 1
```

[PreviousEnable Share URL](https://docs.umami.is/docs/enable-share-url) [NextEnable Cloudflare headers](https://docs.umami.is/docs/enable-cloudflare-headers)

On this page