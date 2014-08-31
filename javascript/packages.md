# Package Management

[Npmjs](http://npmjs.org) should be used for package management, when possible. In addition, [bower.io](http://bower.io/) may be used when necessary to serve static assets.

Assets should be required to either the precision of a major (with the `^` symbol) or minor (with the `~` symbol), depending how often the particular codebase is wont to change. For true semver packages, the precision of a major version is preferred.

When applicable, the "scripts" property of the `package.json` should be used; `npm start` should boot the project, `npm test` should run unit tests, etc.