# Source: https://docs.umami.is/docs/guides/running-on-digitalocean

Menu

Hosting

# Running on DigitalOcean

Copy page

[DigitalOcean](https://m.do.co/c/c9ebc1c0928d) is an affordable cloud hosting provider that will let you host your own Umami setup. In this setup guide we are going to install [Ubuntu](https://ubuntu.com/), a [PostgreSQL](https://www.postgresql.org/) or [MySQL](https://www.mysql.com/) database, an [Nginx](https://www.nginx.com/) webserver, [Node.js](https://nodejs.org/) and Umami. DigitalOcean also has a [NodeJS droplet build](https://marketplace.digitalocean.com/apps/nodejs) that comes with Node.js, Ubuntu and Nginx which can get you started quicker.

For personal use, you can start with a single $5 a month cloud server and scale up as needed. You can use this **[link](https://m.do.co/c/c9ebc1c0928d)** to get a $100 credit for the first 60 days.

Note, these steps can be repeated on any cloud hosting provider that offers Ubuntu.

## Install Ubuntu[#](https://docs.umami.is/docs/guides/running-on-digitalocean#install-ubuntu)

- [Initial server setup with Ubuntu 20.04](https://www.digitalocean.com/community/tutorials/initial-server-setup-with-ubuntu-20-04)

## Install database (PostgreSQL or MySQL)[#](https://docs.umami.is/docs/guides/running-on-digitalocean#install-database-postgresql-or-mysql)

- [How to install PostgreSQL on Ubuntu 20.04](https://www.digitalocean.com/community/tutorials/how-to-install-postgresql-on-ubuntu-20-04-quickstart)
- [How to install MySQL on Ubuntu 20.04](https://www.digitalocean.com/community/tutorials/how-to-install-mysql-on-ubuntu-20-04)

## Install Nginx[#](https://docs.umami.is/docs/guides/running-on-digitalocean#install-nginx)

- [How to install Nginx on Ubuntu 20.04](https://www.digitalocean.com/community/tutorials/how-to-install-nginx-on-ubuntu-20-04)

## Install Node.js[#](https://docs.umami.is/docs/guides/running-on-digitalocean#install-nodejs)

- [How to install Node.js on Ubuntu 20.04](https://www.digitalocean.com/community/tutorials/how-to-install-node-js-on-ubuntu-20-04)

## Install Umami[#](https://docs.umami.is/docs/guides/running-on-digitalocean#install-umami)

- See [Install](https://docs.umami.is/docs/install) under **Getting started**

## Running Umami[#](https://docs.umami.is/docs/guides/running-on-digitalocean#running-umami)

You can simply run `npm start` to start Umami, but it's highly recommended you use a process manager like [PM2](https://pm2.keymetrics.io/) which will handle restarts for you.

To run with PM2:

```shell
npm install pm2 -g
cd umami
pm2 start npm --name umami -- start
pm2 save
```

## Proxying with Nginx[#](https://docs.umami.is/docs/guides/running-on-digitalocean#proxying-with-nginx)

With Umami now running, you can proxy requests to a domain or subdomain from Nginx to Umami.

The following config will send all requests from `umami.yourdomain.com` to your local Umami instance.

```nginx
server {
  server_name umami.yourdomain.com;

  location / {
    proxy_pass http://localhost:3000;
    proxy_set_header X-Real-IP $remote_addr;
    proxy_set_header Host $host;
    proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
  }
}
```

The following config will allow you to host Umami at a subpath for your domain (eg: website.com/stats). This requires setting the environment variable `BASE_PATH=/stats` in your `.env` file.

```nginx
server {
  ...
  location /stats/_next/static/ {
    alias /your_install_location/umami/.next/static/;
    access_log off;
    expires max;
  }
  location /stats {
    proxy_pass http://127.0.0.1:3000;
    proxy_set_header X-Real-IP $remote_addr;
    proxy_set_header Host $host;
    proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
  }
  ...
}
```

## Adding an SSL certificate (optional)[#](https://docs.umami.is/docs/guides/running-on-digitalocean#adding-an-ssl-certificate-optional)

- [How To Secure Nginx with Let's Encrypt on Ubuntu 20.04](https://www.digitalocean.com/community/tutorials/how-to-secure-nginx-with-let-s-encrypt-on-ubuntu-20-04)

## Finish[#](https://docs.umami.is/docs/guides/running-on-digitalocean#finish)

That's it! You're now self-hosting Umami on your own server.

[PreviousRunning on Cloudzy](https://docs.umami.is/docs/guides/running-on-cloudzy) [NextRunning on Fly.io](https://docs.umami.is/docs/guides/running-on-fly-io)

On this page