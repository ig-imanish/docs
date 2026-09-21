# Source: https://docs.umami.is/docs/guides/running-on-railway

Menu

Hosting

# Running on Railway

Copy page

[Railway](https://railway.app/) is attempting to build software development infrastructure for humans. It's founded with the core ideology that building software should be "Take what you need, leave what you don't" and that the current iteration of tools for software development is far too complicated for current generations of developers, let alone the ones that come next. As a result, Railway handles your builds, deployments, scaling, and management of infrastructure; from development to production!

Railway provides a free hosting services which allows you to deploy Umami and set up a PostgreSQL database so you can have your self-hosted version at the click of a button.

## Setup Website and Database[#](https://docs.umami.is/docs/guides/running-on-railway#setup-website-and-database)

### Railway Button (Recommended)[#](https://docs.umami.is/docs/guides/running-on-railway#railway-button-recommended)

[![Deploy on Railway](https://railway.app/button.svg)](https://railway.app/new/template/umami-analytics)

Click the button above to deploy your self-hosted version of the Umami website along with an automagically provisioned PostgreSQL database.

You should now be able to visit your Umami dashboard and set up sites that you want to track analytics for.

You can find the URL in your project dashboard which you can visit by running `railway open`.

## Running on Railway from a forked repository[#](https://docs.umami.is/docs/guides/running-on-railway#running-on-railway-from-a-forked-repository)

The previously described method is the quickest and easiest way to get Umami up and running on Railway. However, this creates a new repository with a single commit under your GitHub account. You may want to use a forked repository instead to be able to conveniently receive updates from (or contribute pull requests to) the Umami source repository via GitHub.

### Set up Railway project[#](https://docs.umami.is/docs/guides/running-on-railway#set-up-railway-project)

1. Fork the [Umami repository](https://github.com/umami-software/umami).
2. Create an account on [Railway](https://railway.app/) connected to GitHub.
3. If you wish, you can give Railway permission only to your Umami fork repository when linking your GitHub account.
4. From the dashboard page click **New Project > Deploy from repo**.
5. Choose your forked Umami repository and select the **master** branch.
6. Add a first variable called `PORT`, set its value to a valid port number (eg: `3000`). Click **Add**.
7. Add a second variable called `DATABASE_TYPE`, set its value to `postgres`. Click **Add**.
8. Add a third variable called `HOSTNAME`, set its value to `0.0.0.0`. Click **Add**.
9. Click **Deploy**.

This initial deploy will fail until you follow the rest of these steps.

### Database and Deploy[#](https://docs.umami.is/docs/guides/running-on-railway#database-and-deploy)

1. Close the settings sidebar and click **New**, click **Database** and select **Add PostgreSQL**.
2. On the dashboard, select your Umami service, go to the **Variables** tab and click **New Variable**.
3. Click **Add Reference** and select the `DATABASE_URL` variable from your Postgres database. Click **Add**.

Adding the database should trigger a re-deploy, and clicking the app link should get you to the login page of your Umami instance.

Troubleshooting

If Railway states `Your project has no deploys` within your dashboard.

1. Select `Set up your project locally` in the bottom left hand corner.

2. Within the `umami` root directory follow the instructions within the pop up.

- Login to your Railway account with `railway login`
- Link your project with `railway link`
- Open your project dashboard with `railway open`
- Upload and deploy your project with `railway up`

3. Follow the **Getting started** guide starting from the [Login](https://docs.umami.is/docs/login) step and be sure to change the default password.

Notes

- Read more about [adding a website](https://umami.is/docs/add-a-website) and [collecting data](https://umami.is/docs/collect-data) here

[PreviousRunning on Qovery](https://docs.umami.is/docs/guides/running-on-qovery) [NextRunning on Sevalla](https://docs.umami.is/docs/guides/running-on-sevalla)

On this page