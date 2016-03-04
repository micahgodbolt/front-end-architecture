## Getting Task Runners into Your Project

### Grunt

```js
module.exports = function(grunt) {
 grunt.loadNpmTasks('grunt-sass');  
 grunt.initConfig({
   sass: {
     options: {
     },
     dist: {
       src: 'sass/style.scss',
       dest: 'css/style.css',
     }
   }
 });
 grunt.registerTask('default', [
   'sass'
   ]);
};
```

### Gulp

```js
var gulp = require('gulp');
var sass = require('gulp-sass');
gulp.task('default', function () {
   gulp.src('./*.scss')
       .pipe(sass())
       .pipe(gulp.dest('./css'));
});
```
