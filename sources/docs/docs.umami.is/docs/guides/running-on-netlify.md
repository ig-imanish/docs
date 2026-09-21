# Source: https://docs.umami.is/docs/guides/running-on-netlify

Menu

Hosting

# Running on Netlify

Copy page

[Netlify](https://netlify.com/) provides a free hosting service which is ideal for GitHub organizations.

In this setup, you should already have a database server running and accepting remote connections. If you don't already have a database, you can follow the [Running on DigitalOcean](https://docs.umami.is/docs/guides/running-on-digitalocean) guide to get a database up and running. You can also check out the **Managed databases** section under [Hosting](https://docs.umami.is/docs/guides/hosting).

## Setup[#](https://docs.umami.is/docs/guides/running-on-netlify#setup)

[![Deploy with netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/umami-software/umami)

_Automate steps 1-5 using the button above_

1. Fork the [https://github.com/umami-software/umami](https://github.com/umami-software/umami) project to your GitHub account.
2. Create an account on [Netlify](https://netlify.com/).
3. From the dashboard page click **Import Project** then specify the URL to your fork of the project on GitHub.
4. Change build command to **yarn run build**.
5. Add the required environment variables `DATABASE_URL`. These values are defined in the **Configure Umami** step from [Install](https://docs.umami.is/docs/install).
6. Deploy and visit your application.
7. Follow the **Getting started** guide starting from the [Login](https://docs.umami.is/docs/login) step and be sure to change the default password.

[PreviousRunning on Neon Postgres](https://docs.umami.is/docs/guides/running-on-neon) [NextRunning on Nodion](https://docs.umami.is/docs/guides/running-on-nodion)

On this page