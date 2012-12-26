# duckJS

__A pure-JavaScript CSS selector engine designed to be easily dropped in to a host library.__

More information: http://duckJS.com/

Discussion: https://github.com/superRaytin/duckJS/wiki/

Documentation: https://github.com/superRaytin/duckJS/wiki/duckJS-Documentation

Browser support: https://github.com/superRaytin/duckJS/wiki/

Testing Sizzle:
 - run `make` to pull down QUnit from github, which is the only thing the Makefile does.
 - Open test/index.html in your browser to run the tests.
 - The actual unit tests are in test/unit/selectors.js and test/unit/utilities.js.

Developing Sizzle with grunt:
 - `grunt` and `grunt lint` will lint sizzle.js and the tests.
 - `grunt watch` can be run to re-lint files as you change them
