# Source: https://docs.umami.is/docs/updates

Menu

Umami

# Getting updates

Copy page

## Source code[#](https://docs.umami.is/docs/updates#source-code)

Make sure you are in the Umami project directory before running these commands.

Pull the latest changes from the Git repository:

```shell
git pull
```

Install any new or updated dependencies:

```shell
pnpm install
```

Rebuild the project:

```shell
pnpm build
```

Finally, restart the application:

```shell
pnpm start
```

If you are using a process manager like PM2, restart the process instead:

```shell
pm2 restart umami
```

## Docker[#](https://docs.umami.is/docs/updates#docker)

Pull the latest image:

```shell
docker pull docker.umami.is/umami-software/umami:latest
```

Then restart your container to use the new image. If using Docker Compose:

```shell
docker compose down
docker compose up -d
```

## Refresh database statistics after upgrading[#](https://docs.umami.is/docs/updates#refresh-database-statistics-after-upgrading)

Major upgrades (such as moving to v3) run schema migrations that can leave PostgreSQL's query planner with stale statistics, making dashboard queries slower than expected on large instances. Run `ANALYZE` to refresh them:

```sql
ANALYZE;
```

This is safe to run on a live database and completes quickly. Afterward, dashboard queries should return to their expected speed.

[PreviousInstallation](https://docs.umami.is/docs/install) [NextLogin](https://docs.umami.is/docs/login)

On this page