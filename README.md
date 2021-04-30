## Please Don't Use

> Please use `npm init remix` instead of this starter repo to create a new Remix app.
> This repository was archived on April 29, 2021.

# Remix Starter for Vercel

Welcome to Remix!

This is a starter repo for using [Remix](https://remix.run) with [Vercel](http://vercel.com/).

## Development

After cloning the repo, rename `.npmrc.example` to `.npmrc` and insert the license key you get from [logging in to your dashboard at remix.run](https://remix.run).

> Note: if this is a public repo, you'll probably want to move the line with your key into `~/.npmrc` to keep it private.

Then, install all dependencies using `npm`:

```sh
$ npm install
```

Your `@remix-run/*` dependencies will come from the Remix package registry.

### First Run

Before you can run the app in development you need link the project to a new vercel project on your account.

```sh
$ vercel link
```

Follow the prompts, and when its done you should be able to get started:

```sh
$ npm start
```

This will start the Remix's build watcher and the vercel development server.

## Deploying to Production

You will need to add your npmrc with your Remix token inside it to your environments:

```bash
$ vercel env add plain NPM_RC development < .npmrc
$ vercel env add plain NPM_RC preview < .npmrc
$ vercel env add plain NPM_RC production < .npmrc
```

Once that's done you can deploy!

```sh
$ npm run build
$ vercel
```

## Documentation

Detailed documentation for Remix [is available at remix.run](https://remix.run/dashboard/docs).
