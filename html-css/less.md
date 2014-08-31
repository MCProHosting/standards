# Notes on LESS

For larger projects, it is very beneficial to use a preprocessor, and we use LESS.

Do not put vendor prefixes in your stylesheets. They will be automatically added during [processing](html-css/processing.md).

The "main" CSS file which should be compiled, should be named `style.less` and compile into a file called `style.css`. All files which should not be compiled directly, should be prefixed with an underscore.

The only function of the `style.less` is to declare variables which are used by *multiple* imports, and import other LESS. Variables which do not need to be used outside of their own individual files should be declared in the first lines of the file they are used in.

> Note for using Bootstrap: It's a good idea to only import the parts of Bootstrap which are needed for the application. [Open source example here](https://github.com/connor4312/getspigot/blob/master/src/css/bootstrap/_index.less).