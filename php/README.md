# PHP

You must follow the [PSR-2](https://github.com/php-fig/fig-standards/blob/master/accepted/PSR-2-coding-style-guide.md) standards when developing code - they cover most general formatting subjects.

The use of the Composer package manager is encouraged. When developing new Composer-based packages, it is recommended to use the PSR-4 autoloading mode.

### Documentation

Document your code using phpDoc format when appropriate. Comments within the code are a good thing!

### Leaning Forward...

You should program for PHP 5.5 and onwards - do not use functions that are deprecated in the most recent version of PHP. `eval()` functions should *never* be used in PHP except in purely development tools.

When connecting to SQL databases, the PDO adapter is preferred for its wide use range and flexibility. The age-old MySQL adapter must not be used for any code developed developed for MCPH under any circumstances.
