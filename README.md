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

push only the dist folder to the gh-pages branch:
```
git subtree push --prefix dist origin gh-pages

```

in repo _Actions_ tab run 'Deploy static content to Pages' workflow
