# Source: https://docs.umami.is/docs/guides/running-on-neon

Menu

Hosting

# Running on Neon Postgres

Copy page

[Neon](https://neon.tech/) is a fully-managed serverless Postgres service.

## Setup[#](https://docs.umami.is/docs/guides/running-on-neon#setup)

1. Create a project on Neon with a given name in a region close to where you will be hosting your Umami project.
 - You can also create a Neon project with the Neon CLI: `npx neonctl projects create`. The connection string will be printed to the console.
2. Get the database connection string with pooled connection enabled. It should look something like this: `postgres://user:passwd@endpoint-pooler.region.aws.neon.tech/neondb`.
 - You can also get the connection string with Neon CLI: `npx neonctl connection-string --project-id <project-id> --pooled`.
3. **Important:** add `?pgbouncer=true&connect_timeout=10` to the connection string you just copied.
4. Add `DATABASE_URL` to your `.env` file:

    ```text
    DATABASE_URL=postgres://user:passwd@endpoint-pooler.region.aws.neon.tech/neondb?pgbouncer=true&connect_timeout=10
    ```

5. You should now be able to check the database connection and update the schema (`yarn run build-db && yarn run update-db`).
6. Follow the **Getting started** guide starting from the [Login](https://docs.umami.is/docs/login) step and be sure to change the default password.

[PreviousRunning on Kubernetes with HelmForge](https://docs.umami.is/docs/guides/running-on-helmforge) [NextRunning on Netlify](https://docs.umami.is/docs/guides/running-on-netlify)

On this page