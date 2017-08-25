# webpack-configuration !
The purpose of this repository is to demonstrate with some code samples the ease with which Webpack can be configured.

[Webpack](https://webpack.github.io/docs/) is a popular module bundler, a tool for bundling application source code in convenient chunks and for loading that code from a server into a browser. Webpack is a powerful module bundler. A bundle is a JavaScript file that incorporates assets that belong together and should be served to the client in a response to a single file request. A bundle can include JavaScript, CSS styles, HTML, and almost any other kind of file.

Webpack roams over your application source code, looking for import statements, building a dependency graph, and emitting one or more bundles. With plugins and rules, Webpack can preprocess and minify different non-JavaScript files such as TypeScript, Javascript, Html, Image, SASS, and LESS files.

You determine what Webpack does and how it does it with a JavaScript configuration file, `webpack.config.js`.

Developers typically have separate configurations for development, production, and test environments. All three have a lot of configuration in common. A good practice is to create separate configurations for each environment and gather the common configuration in a file called webpack.common.js. 

So we end up with the following files:
* `config/webpack.common.js` *- this file does most of the heavy lifting.*
* `config/webpack.dev.js` *- this file contains the DEV envt. specific configuration.*
* `config/webpack.prod.js` *- this file contains the PROD envt. specific configuration.*
* `config/webpack.test.js` *- this file contains the TEST envt. specific configuration.*
* `webpack.config.js` *- this file lives in the root folder, and uses `webpack-merge` to combine the Commom configuration with the required Envt. specific configuration and provides it to Webpack to compile.*

To build targetting an environment (e.g.: PROD)), edit file `webpack.config.js` and replace

`module.exports = require('./config/webpack.dev.js');`

with

`module.exports = require('./config/webpack.prod.js');`

You could also code for checking `process.env.NODE_ENV` in `webpack.config.js` and use the appropriate config file.

The code samples work for the following module versions:
* webpack "^3.5.5"
* webpack-dev-server "^2.7.1"
* webpack-merge "^4.1.0"


---
*Source :* [Angular with Webpack](https://v2.angular.io/docs/ts/latest/guide/webpack.html)

*Further reading :* [Webpack](https://webpack.github.io/docs/)

---
##   License

Shared under MIT License.