# React-build-for-dev-guide

To be able to build react with `.env.development` you can do the following:

install dotenv (make sure to add save dev) `npm install dotenv-cli --save-dev`.

In package.json scripts section add new script:
`"build:dev": "dotenv -e .env.development react-scripts build",`

And you can build for development with npm run build:dev.

### Disabling plain `build` 

I also added a `build:prod` and disabled the regular build so that I have to explisitly choose the environment

`"build:dev": "dotenv -e .env.development react-scripts build",` <br>
`"build:prod": "dotenv -e .env.production react-scripts build",` <br>
`"build": "echo \"Please use build:dev or build:prod \" && exit 1",`

> Be aware that if you add a variable to `.env.production` and don't override it in `.env.development` the one from `.env.production` will be declared even if you build for dev.
