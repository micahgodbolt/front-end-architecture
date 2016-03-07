## Grunt PageSpeed

```js
$ npm install grunt-pagespeed --save-dev

// Added to Gruntfile.js
grunt.loadNpmTasks('grunt-pagespeed');

// Added to grunt.initConfig inside of Gruntfile.js
 pagespeed: {
  options: {
    nokey: true,
    url: "http://redhat.com"
  },
  desktop: {
    options: {
      paths: ["/en", "/en/services"],
      locale: "en_US",
      strategy: "desktop",
      threshold: 80
    }
  },
  mobile: {
    options: {
      paths: ["/en", "/en/services"],
      locale: "en_US",
      strategy: "mobile",
      threshold: 80
    }
  }
}
```

## Grunt Perfbudget

```js
$ npm install grunt-perfbudget --save-dev

// Added to Gruntfile.js
grunt.loadNpmTasks('grunt-perfbudget');

perfbudget: {
  default: {
    options: {
      url: 'http://www.redhat.com/en',
      key: 'SEE_NOTE_ABOVE',
      budget: {
        visualComplete: '4000',
        SpeedIndex: '1500'
      }
    }
  }
}
```
