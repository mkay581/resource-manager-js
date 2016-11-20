[![Build Status](https://travis-ci.org/mkay581/resource-manager.svg?branch=master)](https://travis-ci.org/mkay581/resource-manager)
[![npm version](https://badge.fury.io/js/resource-manager.svg)](https://badge.fury.io/js/resource-manager)

# Resource Manager

A library that loads and caches files (and their contents) on-the-fly. Which is extremely helpful when preloading files
in a browser, for instance. All different file types are supported including CSS, JavaScript, and HTML templates.

Note that this package is transpiled using [Babel](https://github.com/babel/babel) and conforms to the [ECMAScript 6](http://es6-features.org/)
standard, allowing it to utilize [fetch](https://fetch.spec.whatwg.org/) calls to make its requests.


## Usage

In order to use carousel, you can use one of the [pre-built files](/dist) if you want to quickly get started. 
Or, alternatively you can install as an npm package.

```
npm install resource-manager-js --save
```


### Load CSS files

```javascript
var cssPaths = ['path/to/css/file', 'path/to/another/css/file'];
ResourceManager.loadCss(cssPaths).then(function () {
    // css files have been loaded!
});
```

### Load JavaScript files

You can load script files dynamically by calling the `loadScript()` method. When called, the supplied script
will be loaded into the `<head>` of the DOM and run immediately.

```javascript
ResourceManager.loadScript('path/to/js').then(function () {
    // script has been loaded!
});
```

### Request data endpoints

The `fetchData()` method makes XHR/ajax requests easy.

```javascript
ResourceManager.fetchData('path/to/data', {cache: true}).then(function (response) {
    // response has been retrieved!
    // print out the response
    console.log(response);
});
```


### Load template files

Load HTML file contents into an already-existing DOM element by using the `loadTemplate()` method.


```javascript
var body = document.body;
ResourceManager.loadTemplate('path/to/html/file', body).then(function () {
    // html contents have been loaded into the body element
});
```
