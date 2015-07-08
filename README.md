# Prelodr
[![](https://img.shields.io/bower/v/prelodr.svg?style=flat-square)](https://github.com/quintana-dev/prelodr#install) [![](https://img.shields.io/npm/v/prelodr.svg?style=flat-square)](https://www.npmjs.com/package/prelodr) [![Build Status](http://img.shields.io/travis/quintana-dev/prelodr.svg?style=flat-square)](https://travis-ci.org/quintana-dev/prelodr) [![Inline docs](http://inch-ci.org/github/quintana-dev/prelodr.svg?branch=master&style=flat-square&v1)](http://inch-ci.org/github/quintana-dev/prelodr)

> A simple Material preloader inspired in Google Inbox.

![image](http://g.recordit.co/0Uc5Bih5Tk.gif)

[View demo](http://codepen.io/joseluisq/full/rVeyXY)

## Install
**Bower**

```sh
$ bower install --save prelodr
```

**Npm**

```sh
$ npm install prelodr
```

## Usage

```js
var prelodr = new Prelodr();

// a) Show prelodr
prelodr.in('Loading...');

// b) Hide prelodr
prelodr.out();
```

### Chaining support
Note: `out(fn)` method supports a optional (fn) callback function.

```js
var prelodr = new Prelodr();

prelodr.in("Initializing...")
       .out(function(done){

          console.info(" 1 second delay... ");
          setTimeout(function(){
            done();
          }, 1000);

       })

       .in("Processing...")
       .out(function(done){

          console.info(" 2 seconds delay... ");
          setTimeout(function(){
            done();
          }, 3000);

       })

       .in("Closing...").out();
```

### jQuery

```js
$('body').prelodr({
  prefixClass: 'prelodr',
  show: function(){
    console.log('Show callback')
  },
  hide: function(){
    console.log('Hide callback')
  }
})

// a) Show prelodr
$('body').prelodr('in', 'Processing...')

// b) Hide prelodr
$('body').prelodr('out')
```

## Options
- `duration` : Timing for show and hide transition.
- `prefixClass` : Prefix class for prelodr. Default is `prelodr` class.
- `show` : Callback when prelodr is shown.
- `hide` : Callback when prelodr is hidden.

## Methods
### Prelodr.in(text)
Show the prelodr.
- `text` _{String}_ : Text for prelodr.

### Prelodr.out(fn)
Hide the prelodr.
- `fn` _{Function}_ : (Optional) Callback function

### Prelodr.setOptions(options)
- `options` _{Object}_ : The custom options.

### Prelodr.setContainer(element)
- `element` _{HTML Element}_ : The element container. Default is `document.body`.

### Prelodr.isVisible()
- Checks if Prelodr is visible (boolean).

## License
MIT license

© 2015 [José Luis Quintana](http://quintana.io)
