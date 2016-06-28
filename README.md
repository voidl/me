# me
A one-page personal website project template.

Live Demo: https://manny-mcmannerton.firebaseapp.com/

Me is the codebase for a one-page personal website that is static and simple. Use it to brand yourself on the internet, similar to an about.me page. It is responsive, very fast, and easy to customize. The design is loosely based on an about.me template, and it uses the best web practices and technologies and top-tier free hosting.

-

## Why
So, why not just use [About.me](https://about.me) or a [similar](https://www.squarespace.com/) service to create your one page site? Boring! More important than saving yourself the monthly or annual price (all you'll need to buy is your custom domain name), you get to add your personal touch to your brand. Plus you'll show off some technical competency.

*Requirements*: You need to know how to 1) open the terminal and paste a few commands and 2) open source files in a text editor.

## Overview

If you want to get straight to the setup, skip [here](#setup).

-

## Setup
Below are the instructions to set up your site. Some of the install instructions will come from the relevant parts of Google Web Starter Kit. Here is an overview of what you'll do:

1. Get a copy of the code.
2. Install the dependencies if you don't already have them.
3. Customize it.
4. Deploy your site on your custom domain.


### Install

To get started, [download](https://github.com/voidl/me/archive/master.zip) or clone the code to a directory on your computer.
If you already have [node.js](https://nodejs.org/en/) installed, just open your terminal and run `$ npm install --global gulp && npm install` in that directory to get started.
![npm install](/docs/term-npm.png?raw=true)

If you need help getting node and gulp set up, go [here](https://github.com/google/web-starter-kit/blob/master/docs/install.md#prerequisites) first and follow the instructions.

From your project directory, run

    gulp serve

And your site should open in the browser, running locally at http://localhost:3000/

![gulp serve](/docs/term-gulp-serve.png?raw=true)
![local site](/docs/site-local.png?raw=true)


Check out [commands](#/docs/commands.md) for more things you can do with gulp and WSK.


### Customize your site
The site content is in the `app` folder, basically in two files: `index.html` and `main.scss`.

In order to start making changes to your site, just open your favorite text editor and load up those two files. With your site still running locally in the browser (from `gulp serve`), you can now make changes to your site and they will update automatically in the browser each time you save. This is because Web Starter Kit comes with browser-sync built in.

![atom index](/docs/atom-index.png?raw=true)

#### Favicons
You can use [Real Favicon Generator](https://realfavicongenerator.net/) to generate your favicons (the little icon in the browser tab and bookmarks).
Create a square icon (500x500px) in a photo editor and save as a PNG. Upload that to generate your icons.

![favicon generator](/docs/favicon-generator.png?raw=true)  

Ignore the instructions (even though there is an option for Google Web Starter Kit - they're [working](https://github.com/google/web-starter-kit/issues/599) on their own favicon solution). Just Download your favicon package (Step 1). Open `/app/images/touch` folder and copy and paste your new favicon files, overwriting the existing files by making sure the names match exactly. Also replace the `favicon.ico` file in the root `app` directory with your new image.

![favicon generator](/docs/favicon-generator-dl.png?raw=true)


### Deploy to host
You can host your site anywhere you can deliver static files (Github Pages, Amazon S3). We'll use Firebase, a Google app hosting platform that [recently announced](https://firebase.googleblog.com/2016/05/firebase-expands-to-become-unified-app-platform.html) a pricing update as part of their big platform update in May, 2016. The free tier was bumped up to 1GB file storage, 10GB transferred, and a custom domain, which is all we need for a static one-page website. Plus, you get a global CDN and an SSL certificate included by default (so you get your :lock: and https://).

![Firebase Pricing](/docs/firebase-pricing.png?raw=true)

It's **very** easy to deploy your app to Firebase. Just head to https://firebase.google.com/ and follow the instructions to *Get Started*.

![Firebase Home](/docs/firebase-home.png?raw=true)

You can use your existing Google account and it will take you straight to the dashboard where you can *Create a New Project*.

![Firebase New](/docs/firebase-new.png?raw=true)

You'll need to install [node.js](https://nodejs.org/en/) in order to use npm on the command line. (It should be installed already from the [Install](#install) step.) The instructions will walk you through running a few commands in the terminal to initiate your project with Firebase.

![Firebase Setup](/docs/firebase-setup-1.png?raw=true)



#### Exceptions ahead!
![Firebase Setup](/docs/firebase-setup-2.png?raw=true)

1. Skip the second step, `firebase init`, because that will overwrite some of our custom deployment settings. Instead, go to your Firebase console and copy your app id (in the image below the app id is test-3417d) and paste that in your `/.firebaserc` file where it says `your firebase app id goes here` (keep the quotes).  
![Firebaserc](/docs/atom-firebaserc.png?raw=true)
![Firebase New App](/docs/firebase-new-app.png?raw=true)

2. Before we run `firebase deploy`, we need to run the `gulp` command by itself in order to build the final site. Once that's finished (around 20 seconds), then run `firebase deploy`.
![Firebase Setup](/docs/term-gulp-deploy.png?raw=true)

Now your site is live on your default firebase app domain name.

![Firebase Site](/docs/site-firebase.png?raw=true)

On Mobile:

![Firebase Mobile](/docs/site-mobile.png?raw=true)

All that's left is to connect your custom domain name from the Firebase app dashboard. If you want to stay on the Google train, head to [Google Domains](https://domains.google.com/registrar) to buy one. (Hint: check out https://domainr.com and https://en.wikipedia.org/wiki/List_of_Internet_top-level_domains to come up with something unique.)

To update your site again you can just 1) make your changes to the appropriate `app` files - run `gulp serve` to preview the changes if you want, 2) run `gulp`, 3) run `firebase deploy`! :boom:

-
## License
[Licensed](https://github.com/google/web-starter-kit/blob/master/LICENSE) under the Apache License, Version 2.0

Cheers,  
Daniel
