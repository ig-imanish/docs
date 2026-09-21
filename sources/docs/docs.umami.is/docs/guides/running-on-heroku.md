# Source: https://docs.umami.is/docs/guides/running-on-heroku

Menu

Hosting

# Running on Heroku

Copy page

> [Heroku](https://www.heroku.com/) is a container-based cloud Platform as a Service (PaaS). Developers use Heroku to deploy, manage, and scale modern apps. The platform is elegant, flexible, and easy to use, offering developers the simplest path to getting their apps to market.
> 
> From the ["What is Heroku?" section](https://www.heroku.com/about) of their website.

Heroku provides a hosting service which works with Umami as well as databases through add-ons. You don't need to have a database set up before this setup guide.

## Setup[#](https://docs.umami.is/docs/guides/running-on-heroku#setup)

[![Deploy](https://www.herokucdn.com/deploy/button.svg)](https://heroku.com/deploy?template=https://github.com/umami-software/umami)

_Automate all steps using the button above_

### Website[#](https://docs.umami.is/docs/guides/running-on-heroku#website)

1. Fork a copy of the [Umami repository](https://github.com/umami-software/umami).
2. Create an account on [Heroku](https://heroku.com/).
3. From the dashboard page click **New > Create new app**.
4. Choose an **App name** and then click **Create app**.
5. Under **Deployment method** click **GitHub** and follow the instructions to connect Heroku to GitHub.
6. Search for the repository and click **Connect**.

### Database[#](https://docs.umami.is/docs/guides/running-on-heroku#database)

1. Navigate to the **Resources** tab and click on the **Find more add-ons** button.
2. Search for **Heroku Postgres** and follow its instructions to install the add-on.
3. The add-on will set the `DATABASE_URL` automatically; you should not have to manually set it.
4. You will need to set up the database tables by following the **Create database tables** section of the [Install](https://docs.umami.is/docs/install) docs. You can find temporary connection details by following the **Resources > Heroku Postgres > Settings > Database Credentials** path. To run commands found in the docs click **More > Run Console**.

### Build and Deploy[#](https://docs.umami.is/docs/guides/running-on-heroku#build-and-deploy)

1. With the environment variables and database set up, click the **Deploy > Manual Deploy > Deploy Branch** button.
2. Once the build has finished, the website should be live. Follow the **Open app** button at the top of the dashboard to view it.
3. Follow the **Getting started** guide starting from the [Login](https://docs.umami.is/docs/login) step.

[PreviousRunning on Forge](https://docs.umami.is/docs/guides/running-on-forge) [NextRunning on Koyeb](https://docs.umami.is/docs/guides/running-on-koyeb)

On this page