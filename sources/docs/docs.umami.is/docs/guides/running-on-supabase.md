# Source: https://docs.umami.is/docs/guides/running-on-supabase

Menu

Hosting

# Running on Supabase

Copy page

[Supabase](https://supabase.com/) is an open source Firebase alternative built on the Postgres database.

## Setup[#](https://docs.umami.is/docs/guides/running-on-supabase#setup)

1. Edit db/postgresql/schema.prisma to add directUrl = env("DIRECT\_DATABASE\_URL")

2. Create a project on Supabase with a given name in a region close to where you will be hosting your Umami project.

3. Get the database connection string from the **Settings > Database** page, then scroll to the bottom for the **Connection Pooling** section and copy the **Connection string**.

4. Add `DATABASE_URL` and `DIRECT_DATABASE_URL` to your `.env` file:

    ```dotenv
    DATABASE_URL=postgres://[db-user].[project-ref]:[db-password]@aws-0-[aws-region].pooler.supabase.com:6543/[db-name]?pgbouncer=true&connection_limit=1
    DIRECT_DATABASE_URL=postgres://postgres.[my-supabase-project-id]:[db-password]@aws-0-[aws-region].pooler.supabase.com:5432/postgres
    ```

5. You should now be able to build and start Umami (`npm run build` followed by `npm start`).

6. Follow the **Getting started** guide starting from the [Login](https://docs.umami.is/docs/login) step and be sure to change the default password.

[PreviousRunning on Sevalla](https://docs.umami.is/docs/guides/running-on-sevalla) [NextRunning on Vercel](https://docs.umami.is/docs/guides/running-on-vercel)

On this page