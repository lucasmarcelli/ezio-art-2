# ezio-art

## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### To build for production

Ensure that the `publicPath` in vue.config.js is set to the repo name

on `main` build the static site:
```
npm run build
```

Commit and push the built site to github, it should automatically build into `./dist` which will trigger redeploying the site to github pages. The workflow can also be run manually from the _Actions_ tab
