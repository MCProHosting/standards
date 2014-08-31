# Assets

All assets should be compiled using [Gulpjs](http://gulpjs.com/).

 * The default task should run subtasks necessary to make the application functional, and nothing more.
 * There must be a `dist` task, where applicable, which minifies assets.
 * There may be a `spy` task, which runs Gulp to watch files for changes, recompiling and reloading the browser on change.
 * There may be a `lint` task where applicable, which runs [jshint](http://www.jshint.com/) and [jscs](https://github.com/jscs-dev/node-jscs)

The repository [connor4312/gulp-breakout](https://github.com/connor4312/gulp-breakout) serves as the basis for most repositories, and may be used for reference.

### Browserify

When developing complex client-side applications, the use of [Browserify](http://browserify.org/) is highly recommended.

> Warning! Care should be taken with Browserify. It is easy to simply require npm modules, but by doing so you may be including a huge amount of dependencies or even multiple versions/builds of the same package! This can make your filesize explode very quickly. Require responsibly!