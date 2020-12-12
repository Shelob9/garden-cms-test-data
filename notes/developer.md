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
 - Digital Garden Site - The website for one digital garden. Hosted using Github pages, by default.
  - These sites are generated using the [[garden-client]], which is a [React]() app built with the [NextJS](https://nextjs.org) framework.
 - Digital Garden Server - CRUD API that uses Github, specifically the content repo mentioned above, for storage. Also it has the UI for installation and login.
  - The [[garden-server]] is also a React/ NextJS app. [DigitalGardenBuilder.app](https://DigitalGardenBuilder.app) is deployed using [Vercel](https://vercel.com/). You could probably use Netlify or Serverless Framework.
