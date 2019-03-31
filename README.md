# learning-mdc-for-vue
Learning Material Components for Web (v1.1.0) with Vue CLI

## Precondition:
- Microsoft Visual Code is installed
- npm install -g @vue/cli@3.5.3

## Guide
1. Open CLI
2. ```vue create <app-name>```
3. Manually Select features
4. Choose the following:
	Babel
	Router
	CSS Pre-processors
	Linter / Formatter
5. Use history mode for router? => Y
6. Sass/SCSS (with node-sass)
7. ESLint + Prettier
8. Lint on save
9. In dedicated config files
10. Save this as a preset for future projects? => N

...wait for setup to finish...

11. ```cd <app-name>```
12. ```npm install --save-dev material-components-web@1.1.0```

13. ```code vue.config.js```
```js
module.exports = {
    // publicPath: '',
    css: {
        loaderOptions: {
            sass: {
                includePaths: ['./node_modules']
            }
        }
    }
}
```

14. ```code .```

Then just follow the docs at ```./node_modules/@material```


## Project setup
```
npm install
```

### Compiles and hot-reloads for development
```
npm run serve
```

### Compiles and minifies for production
```
npm run build
```

### Run your tests
```
npm run test
```

### Lints and fixes files
```
npm run lint
```

### Customize configuration
See [Configuration Reference](https://cli.vuejs.org/config/).
