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

build the static site:
```
npm run build
```

commit it:
```
git add dist && git commit -m '<commit message>'
```

push only the dist folder to `gh-pages`:
```
git subtree push --prefix dist origin gh-pages
```

this should trigger the redeploy but if `gh-pages` isn't the default branch it won't so you can run the workflow manually from the _Actions_ tab
