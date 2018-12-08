# Gatsby & GitHub Pages Tutorial

This tutorial explains how to add a GitHub page generated by [Gatsby](https://www.gatsbyjs.org/) to your GitHub repo.

> Note: you need to install gatsby globally: `npm install --global gatsby-cli`

### Create Gatsby Project
Open a terminal, navigate to your git repo and create a new gatsby project by running:
```shell
gatsby new gatsby-page
```
> I'm using a [template](https://github.com/codebushi/gatsby-starter-stellar) in this tutorial: `gatsby new gatsby-page https://github.com/codebushi/gatsby-starter-stellar`

### Install gh-pages
Install `gh-pages` for your project:
```shell
cd gatsby-page
npm install gh-pages --save-dev
```
### Configure Gatsby
Add a deploy script to `gatsby-page/package.json`.
```js
{
  "scripts": {
    "deploy": "gatsby build --prefix-paths && gh-pages -d public"
  }
}
```
Now you need to add the name of your repo as `pathPrefix` to `gatsby-page/gatsby-config.js`. In this case:
```js
module.exports = {
  pathPrefix: "/gatsby-gh-pages-tutorial",
}
```
This is where the page will be available.

### Deploy Page
Deploy the page by running the deploy script:
```shell
npm run deploy
```
This will create a `gh-pages` branch and copy everything from `gatsby-page/public` there.

The page should now be available at [andreaswilli.github.io/gatsby-gh-pages-tutorial](https://andreaswilli.github.io/gatsby-gh-pages-tutorial).
> Note: It can take several minutes. If it doesn't work after waiting some minutes, check the configuration in repo settings.
