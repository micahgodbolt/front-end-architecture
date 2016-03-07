## Setting Up Grunt

```
npm i --save-dev git://github.com/anselmh/grunt-phantomcss.git
```

```js
grunt.loadNpmTasks('grunt-phantomcss');

/...
phantomcss: {
  options: {
    mismatchTolerance: 0.05,
    screenshots: 'baselines',
    results: 'results',
    viewportSize: [1280, 800],
    },
    src: [
       'phantomcss.js'
    ]
}
/...
```

## Making It Our Own

```js

// Gruntfile.js
phantomcss: {
  webrh: {
    options: {
      mismatchTolerance: 0.05,
      screenshots: 'baselines',
      results: 'results',
      viewportSize: [1280, 800],
    },
    src: [
       // select all files ending in -tests.js
       'src/library/**/*-tests.js'
    ]
  },
}

```

## Test Portability

```js
// cta.tests.js
casper.thenOpen('http://localhost:9001/cta.html')
    .then(function () {
        this.viewport(600, 1000);
        phantomcss.screenshot('.rh-cta-link', 'cta-link');
    })
    .then(function () {
        this.mouse.move(".rh-cta-link");
        phantomcss.screenshot('.rh-cta-link', 'cta-link-hover');
    });

// quote.tests.js
casper.thenOpen('http://localhost:9001/quote')
    .then(function () {
        this.viewport(600, 1000);
        phantomcss.screenshot('.rh-quote', 'quote-600');
    })
    .then(function () {
        this.viewport(350, 1000);
        phantomcss.screenshot('.rh-quote', 'quote-350');
    });
```
