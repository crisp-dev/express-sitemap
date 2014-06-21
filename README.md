#express-sitemap [![Build Status](https://travis-ci.org/hex7c0/express-sitemap.svg?branch=master)](https://travis-ci.org/hex7c0/express-sitemap) [![NPM version](https://badge.fury.io/js/express-sitemap.svg)](http://badge.fury.io/js/express-sitemap)

sitemap for [expressjs](http://expressjs.com/) 4

## Installation

Install through NPM

```
npm install express-sitemap
```
or
```
git clone git://github.com/hex7c0/express-sitemap.git
```

## API

inside expressjs project
```js
var sitemap = require('express-sitemap')();
var app = require('express')();

sitemap.generate(app);
```

### methods

reset prototype Object for sitemap
```js
sitemap.reset();
```

generate prototype Object for sitemap
```js
sitemap.generate(app);
```

generate prototype Object for sitemap if you use middleware or dynamic building
```js
sitemap.tickle();
```

write sitemap Object to file
```js
sitemap.XMLtoFile();
```

write robots.txt to file
```js
sitemap.TXTtoFile();
```

write both to files
```js
sitemap.toFile();
```

stream sitemap to web
```js
sitemap.XMLtoWeb(res);
```

stream robots.txt to web
```js
sitemap.TXTtoWeb(res);
```

### sitemap(options)

 - `http` - **String** Website HTTP protocol (http | https) *(default "http")*
 - `url` - **String** Website URL *(default "127.0.0.1")*
 - `port` - **Number** Website Port *(default "80")*
 - `sitemap` - **String** Name of sitemap file *(default "sitemap.xml")*
 - `robots` - **String** Name of robots file *(default "robots.txt")*
 - `route` - **Object** Add extra information to sitemap related to this [documentation](http://www.sitemaps.org/protocol.html#xmlTagDefinitions) *(default "disabled")*
  - `lastmod` - **Date** Integrity not controlled
  - `changefreq` - **String** Integrity not controlled
  - `priority` - **Float** Integrity not controlled
  - `disallow` - **Boolean** Flag for disallow this route from parsing *(default "false")*
 - `map` - **Object** Force route (<loc>) detection and building *(default "disabled")*
 - `generate` - **Object** Fastly generate sitemap from express app *(default "disabled")*

you can use ```route:{'ALL': {}}``` if you want propagate extra information to all your urls

#### Examples

Take a look at my [examples](https://github.com/hex7c0/express-sitemap/tree/master/examples)

_Middleware is incompatible http://expressjs.com/4x/api.html#app.use, you can use [tickle](https://github.com/hex7c0/tickle)_

## License
Copyright (c) 2014 hex7c0

Licensed under the GPLv3 license
