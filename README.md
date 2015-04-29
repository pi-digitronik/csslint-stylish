# csslint-stylish
> Stylish formatter for CSSLint

## Usage

### CSSLint Node.js API

To use it with the `csslint` api, you will have to call `csslint` as well as assemble the report, manually.

```js
var csslint = require('csslint');
var csslintStylish = require('csslint-stylish');

var report = csslint.verify(/* css as string here */);

// Format the report stylishly
var stylishReport = csslintStylish.startFormat() + csslintStylish.formatResult(report) + csslintStylish.endFormat();

// Then write it to the console
console.log(stylishReport);
```

### `csslint` CLI
It's currently not possible to use a custom formatter with the CLI.

I have a PR with `csslint` that would make it possible. See <https://github.com/CSSLint/csslint/pull/593>

### `gulp-csslint`
It's currently not possible to use a custom formatter with the gulp-plugin.

See <https://github.com/lazd/gulp-csslint/pull/21>

### `grunt-contrib-csslint`
It's currently not possible to use a custom formatter with the grunt-plugin.

I have no PR there (yet). Feel free to create one!

## API

### csslintStylish.formatResult(report, filename, options)

#### report
Type: `Object`
Optional: false

The report generated by calling `csslint.verify`.

#### filename
Type: `String`
Optional: true

The name of the file linted.

#### options
Type: `Object`
Optional: true

An options-object. Valid options are:

##### absoluteFilePathsForFormatters
Type: `Boolean`
Default: `false`

If `true`, will print the absolute path of the file linted, instead of the relative.
