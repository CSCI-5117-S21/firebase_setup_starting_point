# firebase_setup_starting_point

This repo is intended to be a "starting point" for projects that use firebase and vue, so you can get the "boring" setup work out of the way before lecture.

How I generated this project:

1. `vue create firebase_setup_stating_point` (create basic project template)
2. `vue add router` (update template with vue router)
3. `npm install firebase` (add the firebase web API to this project)

## References:

* <https://savvyapps.com/blog/definitive-guide-building-web-app-vuejs-firebase>

## Project setup (do once after downloading)
1. locally install dependencies with `npm install`
2. On [google firebase console](https://console.firebase.google.com/), create a firebase project for this project
3. configure the firebase API.
    * click the gear on the side-bar and go to project settings
    * at the bottom of this page is a "Your apps" page -- click the `</>` icon to setup the web-api
    * No need to setup firebase hosting right now, we saw that we can do this from the terminal easily enough already. Just register a nickname.
    * It's going to tell you to copy the configuration script into your code. Don't actually do that. Instead we will be using .env and .env.local files to configure this, just copy this data into a temporary file so you don't lose it immediately.
        * .env files are automatically loaded when serving or compiling your project and added to an environment variable.
        * .env.local is also loaded, but it is marked by .gitignore as a file to ignore -- its safe to put api keys and such in this file. (You api key should never go online)
    * update the .env file based on the provided keys
    * copy .env.local.example to .env.local and fill in the api key and appId.
### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
