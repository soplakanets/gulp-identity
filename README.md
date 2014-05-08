# [gulp](http://gulpjs.com)-identity


Does nothing to stream/file. Passes them unchanged.


## Install

```bash
$ npm install --save-dev gulp-identity
```


## Possible usage
Say you need to minify your js file only on production env, you really hate if statements and want your build file to be more readable.

```js
var gulp = require('gulp');

var minifyJs;
if ('production' == process.env.NODE_ENV) {
  minifyJs = require('gulp-uglify');
} else {
  minifyJs = require('gulp-identity');
}

gulp.task('default', function () {
  return gulp.src('src/*.js')
    .pipe(minifyJs())
    .pipe(gulp.dest('dist'));
});
```


## License

[MIT](http://opensource.org/licenses/MIT)