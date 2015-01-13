Newsletters Archive via Mailchimp API
===================

You can see example on [Scala Times](http://www.scalatimes.com/) - Weekly Scala Newspaper.


## Overview

This app is built on the top of [MailChimp API v2.0 NodeJs Example Application](https://github.com/mailchimp/mcapi2-node-examples).


## Running project for the first time

### NodeJS

Install [Node.js](http://nodejs.org/) or check, if you have it installed.
To check, if it's installed, run command `node -v` in console. 
If you see version - than you have it installed. 

If not - go to [http://nodejs.org/](nodejs.org) and install it from there.


### Install dependencies

In console navigate to project's folder and run 

```
  npm install
```

This will install all required dependencies for this project (Express, Jade, Mailchimp API, Cheerio, Underscore).


### Run app

Navigate to `routes/archive.js` file and update Mailchimp API key and List ID.
[Here](http://kb.mailchimp.com/accounts/management/about-api-keys) you can find information on how to find your Mailchimp API key.
[Here](http://kb.mailchimp.com/lists/managing-subscribers/find-your-list-id) you can find information on how 

After that run

```
  MAILCHIMP_API_KEY={YOUR_API_KEY} MAILCHIMP_LIST_ID={YOUR_LIST_ID} node app.js
```

Wait couple of seconds, while you see

```
  campaignsCache is ready
```
in console.

Novigate to `http://localhost:3000/` in your browser.

You should have the latest issue on index page, and archive (last 100 issues) on `http://localhost:3000/archive` page. 


### Fix archive page

To make your archive page properly show excerpts of every newsletter, you need to update function `getCampaignExcerpts()` in `routes/archive.js`.
This function gets HTML of every campaign and finds important information in that HTML.