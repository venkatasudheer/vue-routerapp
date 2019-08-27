# Vue js Router App

> A Vue.js Router project

> Project done by: Manda Venkatasudheer Kumar


## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```


For Component img src resolving if you are using
```
    b-img
    b-img-lazy
    b-card
    b-card-img
    b-card-img-lazy
    b-carousel-slide
    b-embed
```

Step:1  Go to build folder and open vue-loader.conf.js

Step:2  
``` bash
# Replace this code and save it

'use strict'
const utils = require('./utils')
const config = require('../config')
const isProduction = process.env.NODE_ENV === 'production'
const sourceMapEnabled = isProduction
  ? config.build.productionSourceMap
  : config.dev.cssSourceMap

module.exports = {
  loaders: utils.cssLoaders({
    sourceMap: sourceMapEnabled,
    extract: isProduction
  }),
  cssSourceMap: sourceMapEnabled,
  cacheBusting: config.dev.cacheBusting,
  transformToRequire: {
    video: ['src', 'poster'],
    source: 'src',
    img: 'src',
    image: 'xlink:href',
    'b-img': 'src',
    'b-img-lazy': ['src', 'blank-src'],
    'b-card': 'img-src',
    'b-card-img': 'src',
    'b-card-img-lazy': ['src', 'blank-src'],
    'b-carousel-slide': 'img-src',
    'b-embed': 'src'
    
  }
}

```


For a detailed explanation on how things work, check out the [guide](http://vuejs-templates.github.io/webpack/).

