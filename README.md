
You can preview the live site [here](https://ephemeral-wisp-63c6e7.netlify.app/)
# Vue 3 + Vite

This template should help get you started developing with Vue 3 in Vite. The template uses Vue 3 `<script setup>` SFCs, 





## Recommended IDE Setup

- [VS Code](https://code.visualstudio.com/) + [Volar](https://marketplace.visualstudio.com/items?itemName=Vue.volar) (and disable Vetur) + [TypeScript Vue Plugin (Volar)](https://marketplace.visualstudio.com/items?itemName=Vue.vscode-typescript-vue-plugin).


## Prerequisites

Before getting started, here are some tools that you'll want to have installed on your system to make things easier:

Node.js 12 or greater (LTS recommended)

Github CLI

Netlify CLI




Steps to deploy your Vue 3 + Vite App

**Step 1. Scaffold your project with Vite.**

Open up your terminal and run the following command:
```bash
npm create vite@latest YOUR_PROJECT_NAME - --template vue
```

Navigate into your project directory with the following command:

```bash
cd YOUR_PROJECT_NAME
```

**Step 2. Setup Git integration for your project.**

If you're working with a new instance of GitHub CLI, make sure to start by logging in:

```
gh auth login
```

Once you do that, it's time to initialize git in your project by running the following command:

```bash
git init
```
Create a new repo that's connected to your account:
```
gh repo create
```

When prompted on what kind of repo you want to create, select: `Push an existing local repository to GitHub.`

Follow the prompts to fill out the relevant project details.

**Repository name: `YOUR_PROJECT_NAME`**

**Repository Description:**

**Visibility: `Public`**

**This will add an "origin" git remote to your local repository. Continue? `Yes`**


Commit your initial scaffold and push up to the main branch with the following commands:

```bash
# Add all files to staging
git add .

# Commit changes with short message on the change made
git commit -m "feature: scaffold vue 3 and vite project"

# Push changes to main branch
git push origin main
```

**Step 3. Deploy your app**

It's time to connect our new app with Netlify! If you're not logged in already, you can do so by running command below and following the prompts to authenticate the CLI:

```
netlify login
```

Next, we'll want to initialize a brand new project with Netlify using the following command:

```
netlify init
```

Fill out the following prompts for a brand new project:

**What would you like to do? ``Create & configure a new site``**

**Team ``YOUR_TEAM``**

**Site name (optional) ``CHOOSE_UNIQUE_SITE_NAME``**

The following prompts should be have prefilled defaults since Netlify will automatically detect what project you have. So you can just hit enter to use the defaults.

**Your build command (hugo build/yarn run build/etc): ``(vite build)``**

**Directory to deploy (blank for current dir): ``(dist)``**

**Netlify functions folder: ``(netlify/functions)``**

**No netlify.toml detected. Would you like to create one with these build settings? ``(Yes)``**


With that, we're just one step away from finishing the deployment! Because we're using Vue 3 in SPA mode, this means that we'll need to update the ``netlify.toml`` file by uncommenting the ``redirects`` block.

The resulting netlify.toml should look like the following:

```t
# example netlify.toml
[build]
  command = "vite build"
  functions = "netlify/functions"
  publish = "dist"

## Uncomment to use this redirect for Single Page Applications
## Not needed for static site generators.
[[redirects]]
  from = "/*"
  to = "/index.html"
  status = 200
```

Now we just need to commit our change and push it up to our repo with the following commands:

```bash
# Add all files to staging
git add .

# Commit changes with short message on the change made
git commit -m "config: add netlify deploy files"

# Push changes to main branch
git push origin main
```

And because we've hooked up Netlify to our GitHub repo, this means Netlify will automatically pick up the changes and deploy our app!

Step 4. Celebrate!

```
netlify open:site
```

This will open up the website that has been deployed!


```
netlify open
```

Credits to [Netlify](https://www.netlify.com/blog/how-to-deploy-vue-3-and-vite-app-in-5-minutes/)




