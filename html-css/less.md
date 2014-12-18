# Notes on LESS

For larger projects, it is very beneficial to use a preprocessor, and we use LESS.

Do not put vendor prefixes in your stylesheets. They will be automatically added during [processing](html-css/processing.md).

The "main" CSS file which should be compiled, should be named `style.less` and compile into a file called `style.css`. All files which should not be compiled directly, should be prefixed with an underscore. The only function of the `style.less` import other LESS files. Generally our project structure looks something like:
```
 . 
 |-- style.less      < @imports _variables and _index.less's
 |-- _variables.less < Delares 
 |
 |-- bootstrap
 |   |-- _index.less     < @imports bootstrap components, _*.less
 |   |-- _variables.less < Boostrap variable overrides
 |   |-- _forms.less     < Overrides for Bootstrap forms
 |   `-- _buttons.less   < Overrides for Buutstrap buttons
 |
 `-- components
     |-- _index.less    < @imports _*.less
     |-- _features.less < Some feature styling
     `-- _nav.less      < Some nav styling
```

> Note for using Bootstrap: It's a good idea to only import the parts of Bootstrap which are needed for the application. [Open source example here](https://github.com/connor4312/getspigot/blob/master/src/css/bootstrap/_index.less).
