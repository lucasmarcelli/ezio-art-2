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

push only the dist folder to the `gh-pages` branch which should be the deafault branch:
```
git subtree push --prefix dist origin gh-pages

```
if the push to `gh-pages` doesn't trigger the workflow in the _Actions_ tab run the workflow manually
