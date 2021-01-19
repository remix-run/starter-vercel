# Remix Starter for Vercel

Welcome to Remix!

This is a starter repo for using [Remix](https://remix.run) with
[Vercel](http://vercel.com/).

## Development

After cloning the repo, rename `.npmrc.example` to `.npmrc` and insert the license key you get from [logging in to your dashboard at remix.run](https://remix.run).

> Note: if this is a public repo, you'll probably want to move the line with
> your key into `~/.npmrc` to keep it private.

Then, install all dependencies using `npm`:

```sh
$ npm install
```

Your `@remix-run/*` dependencies will come from the Remix package registry.

### First Run

The start script in this project starts a few processes, one of which is `vercel dev`. On your first run, however, you'll need to run `vercel dev` alone to get it set up with Vercel.

```sh
$ vercel dev
```

Follow the prompts, and when the server is started, end it with control + C.

Now whenever you're developing you can use the normal start script:

```sh
$ npm start
```

This will start the Remix development server, a TypeScript watcher for your server code, and the vercel development server.

> Note: In production the Remix asset development server and TypeScript watcher aren't used.

## Deploying to Production

Before you can deploy to production you'll need to turn on "System Environment Variables" on your Vercel app. Log into Vercel and navigate to the app's settings environment variables page:

```
https://vercel.com/<vercel user name>/<name of your app>/settings/environment-variables
```

Check the box that says "Automatically expose System Environment Variables". More info here: https://vercel.com/docs/environment-variables#system-environment-variables

Then you need to add your Remix token to your environments:

```bash
$ vercel env add plain NPM_RC development < .npmrc
$ vercel env add plain NPM_RC preview < .npmrc
$ vercel env add plain NPM_RC production < .npmrc
```

Once that's done you can deploy!

```sh
$ npm run deploy
```

> Note: Typically Vercel builds your app for you when you run `vercel`, but it chokes on TypeScript files and we don't know how to tell it to ignore them. We find it simpler (for now) to just run the build yourself before deploying and telling Vercel to not worry about building for us (you can see in package.json the `vercel-build` command is empty).

## Documentation

Detailed documentation for Remix [is available at remix.run](https://remix.run/dashboard/docs).