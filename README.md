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
git add dist && git commit -m 'adding dist subtree'
```

push only the dist folder to the gh-pages branch, which will trigger a redeploy of the site:
```
git subtree push --prefix dist origin gh-pages
```
