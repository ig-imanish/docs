# Source: https://docs.umami.is/docs/guides/running-on-bunny

Menu

Hosting

# Running on bunny.net

Copy page

[bunny.net](https://bunny.net) is a global platform for content delivery and edge computing. [Magic Containers](https://bunny.net/magic-containers/) lets you deploy and run containerized applications across bunny.net's global network with built-in CDN integration.

You can deploy Umami alongside a PostgreSQL database using Magic Containers.

## Setup[#](https://docs.umami.is/docs/guides/running-on-bunny#setup)

### 1\. Create a new application[#](https://docs.umami.is/docs/guides/running-on-bunny#1-create-a-new-application)

1. Go to **Magic Containers** in the [bunny.net dashboard](https://dash.bunny.net) and click **Add App**.
2. Give your application a name (e.g. `umami`).
3. Choose **Single Region** deployment since this is a stateful application with a database.

### 2\. Add the PostgreSQL container[#](https://docs.umami.is/docs/guides/running-on-bunny#2-add-the-postgresql-container)

1. Click **Add Container**.
2. Enter the name `postgres`.
3. From the **Registry** dropdown, select **DockerHub Public**.
4. Set the image to `library/postgres` and the tag to `16-alpine`.

bunny.net will auto-detect the environment variables. Update them with your preferred values:

- `POSTGRES_USER` = `umami`
- `POSTGRES_PASSWORD` = _choose a strong password_
- `POSTGRES_DB` = `umami`
- `PGDATA` = `/var/lib/postgresql/data/pgdata`

Setting `PGDATA` to a subdirectory of the mount path prevents a permissions conflict between the volume and the PostgreSQL startup process.

Add a 1 GB persistent volume mounted at `/var/lib/postgresql/data`.

### 3\. Add the Umami container[#](https://docs.umami.is/docs/guides/running-on-bunny#3-add-the-umami-container)

1. Click **Add Container**.
2. Enter the name `umami`.
3. From the **Registry** dropdown, select **DockerHub Public**.
4. Set the image to `docker.umami.is/umami-software/umami` and the tag to `postgresql-latest`.

Update the environment variables:

- `DATABASE_URL` = `postgresql://umami:<your-password>@localhost:5432/umami`
- `APP_SECRET` = _a random string used for encryption_
- `DISABLE_TELEMETRY` = `1`

Replace `<your-password>` with the `POSTGRES_PASSWORD` you set in the previous step.

Add a **CDN** endpoint pointing to container port `3000`.

### 4\. Deploy[#](https://docs.umami.is/docs/guides/running-on-bunny#4-deploy)

Review your configuration and click **Confirm and Create**. Once the containers are running, open the CDN endpoint URL to access Umami.

Log in with the default credentials — username `admin` and password `umami` — and change your password immediately under **Settings → Profile**.

Notes

- Both containers run in the same pod and communicate over `localhost`.
- Data is stored in the PostgreSQL persistent volume and survives redeployments.
- You can update the Umami image tag to upgrade to newer versions.
- Read more about [adding a website](https://docs.umami.is/docs/add-a-website) and [collecting data](https://docs.umami.is/docs/collect-data).

[PreviousHosting](https://docs.umami.is/docs/guides/hosting) [NextRunning on CapRover](https://docs.umami.is/docs/guides/running-on-caprover)

On this page