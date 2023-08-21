# Directus on fly.io

## Setup

Start a new fly project:

```sh
  $ fly launch --copy-config --no-deploy
```

Set `PUBLIC_URL` in `fly.toml` to the URL of your project.

Copy `.env.example` to `.env` and set the variables for your setup.

You can get secrets for `KEY` and `SECRET` using the following command:

```sh
  $ openssl rand -hex 32
```

Using [Neon](https://neon.tech/) or
[LiteFS Cloud](https://fly.io/docs/litefs/speedrun/) is highly
recommended for the database.

Load the environment variables:

```sh
  $ cat .env | fly secrets import 
```

## Launch

Deploy the project:

```sh
  $ fly deploy --vm-size shared-cpu-2x
```
