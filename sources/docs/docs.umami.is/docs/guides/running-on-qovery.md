# Source: https://docs.umami.is/docs/guides/running-on-qovery

Menu

Hosting

# Running on Qovery

Copy page

[Qovery](https://www.qovery.com) is a fully-managed cloud platform that runs on your AWS, Digital Ocean and Scaleway account where you can host static sites, backend APIs, databases, cron jobs, and all your other apps in one place.

Qovery provides **free hosting** for individual developers and includes the following:

- Continuous, automatic builds & deploys from GitHub and GitLab.
- Automatic SSL certificates through [Let's Encrypt](https://letsencrypt.org).
- Free managed PostgreSQL.
- Free SSD storage.
- Unlimited collaborators.
- Unlimited [custom domains](https://hub.qovery.com/docs/using-qovery/configuration/application/#domains).

## Setup[#](https://docs.umami.is/docs/guides/running-on-qovery#setup)

### 1\. Create a Qovery Account[#](https://docs.umami.is/docs/guides/running-on-qovery#1-create-a-qovery-account)

Visit the [Qovery dashboard](https://start.qovery.com) to create an account if you don't already have one.

### 2\. Create a project[#](https://docs.umami.is/docs/guides/running-on-qovery#2-create-a-project)

- Click on **Create project** and give a name to your project.
- Click on **Next**.

### 3\. Create a new environment[#](https://docs.umami.is/docs/guides/running-on-qovery#3-create-a-new-environment)

- Click on **Create environment** and give a name (e.g. staging, production).

### 4\. Add your Umami app[#](https://docs.umami.is/docs/guides/running-on-qovery#4-add-your-umami-app)

- Click on **Create an application**, give a name and select your GitHub or GitLab repository where your Umami app is located.
- Define the main branch name and the root application path.
- Click on **Create**.

After the application is created:

- Navigate to your application **Settings**.
- Select **Port**.
- Add port used by your Umami application.

### 5\. Deploy a database[#](https://docs.umami.is/docs/guides/running-on-qovery#5-deploy-a-database)

Create and deploy a new database PostgreSQL database by [following this guide](https://hub.qovery.com/guides/getting-started/create-a-database).

### 6\. Add storage[#](https://docs.umami.is/docs/guides/running-on-qovery#6-add-storage)

To add storage, go to your application **Settings**.

### 7\. Setup your Umami configuration[#](https://docs.umami.is/docs/guides/running-on-qovery#7-setup-your-umami-configuration)

To use PostgreSQL provided by Qovery, you can use the built-in secrets and environment variables. You can read more about environment variables and secrets in our [configuration section](https://hub.qovery.com/docs/using-qovery/configuration/environment-variable/).

### 8\. Deploy the app on Qovery[#](https://docs.umami.is/docs/guides/running-on-qovery#8-deploy-the-app-on-qovery)

All you have to do now is to navigate to your application and click on **Deploy**.

That's it. Watch the status and wait till the app is deployed.

To open the application in your browser, click on **Action** and **Open** in your application overview

## Support[#](https://docs.umami.is/docs/guides/running-on-qovery#support)

Chat with Qovery developers on [Discord](https://discord.qovery.com) if you need help.

[PreviousRunning on PlanetScale](https://docs.umami.is/docs/guides/running-on-planetscale) [NextRunning on Railway](https://docs.umami.is/docs/guides/running-on-railway)

On this page