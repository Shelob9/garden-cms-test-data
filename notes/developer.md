---
title: Digital Garden Builder Developer Documentation 
slug: developer
---
 This is the overview of developer-facing documentation for the Digital Garden Builder. You will not need to be a developer or to read these docs to use the Digital Garden Builder. Please give me a week or two.

The Digital Garden Builder is a Serverless Node.js application, that uses git as a data store. It is free and open-source software. 

- [Github Repository](https://github.com/Shelob9/digitial-garden-builder)


## How It Works
 
 __BTW__ This section is about how this will work in a week or so, not how it currently works. Right now, both the docs site and the server are running on Vercel. There is no static export yet. Installation is not working yet either.
 
 Each digital garden has three parts:
 
 - Content Repo - A git repository with all of the content for the notes, the configuration data and the Github actions for one digital garden.
    - [The Template](https://github.com/Shelob9/garden-builder-content-template)
 - Digital Garden Site - The website for one digital garden. Hosted using Github pages, by default.
  - These sites are generated using the [[garden-client]], which is a [React]() app built with the [NextJS](https://nextjs.org) framework.
 - Digital Garden Server - CRUD API that uses Github, specifically the content repo mentioned above, for storage. Also it has the UI for installation and login.
  - The [[garden-server]] is also a React/ NextJS app. [DigitalGardenBuilder.app](https://DigitalGardenBuilder.app) is deployed using [Vercel](https://vercel.com/). You could probably use Netlify or Serverless Framework.

## Installing For Development

The simplest way to get started is with [gitpod](https://gitpod.io/#https://github.com/Shelob9/digitial-garden-builder).

### Develop Locally

- Clone and install:
 - `git clone git@github.com:Shelob9/digitial-garden-builder.git`
 - `cd digitial-garden-builder`
 - `yarn`
- Read the READMEs for [client](https://github.com/Shelob9/digitial-garden-builder/blob/main/client/README.md) and [server](https://github.com/Shelob9/digitial-garden-builder/blob/main/server/README.md) and set the environment variables for both servers.
- Start servers
 - `yarn dev`
- Run tests
 - `yarn test`
- See in broweser:
 - Client [localhost:3202](https://localhost:3202)
 - Server [localhost:3000](https://localhost:3000)

### Develop With Gitpod

[Click this link](https://gitpod.io/#https://github.com/Shelob9/digitial-garden-builder)

## Deploy With Github Pages

The builder CLI is used to generate a static HTML export of each digital garden and deploy it to Github pages. 

### No custom domain

If there is no custom domain, the url will probably be `<username>.github.io/<repo-name>`. In this case the `USE_REPO_PREFIX` environment variable should be set to true, or CSS and JavaScript will not load correctly.

### Subdomain

If you want to host with a subdomain `garden.<your-domain>.pizza` 

- Set a CNAME record in DNS settings for `<username>.github.io`
- Set your domain in Github pages settings and/or commit a CNAME file to gh-pages branch, in docs directory with the domain name.
- Wait about 15 minutes.
