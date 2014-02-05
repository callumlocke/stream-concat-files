# stream-concat-files

[![NPM version][npm-image]][npm-url] [![Build Status][travis-image]][travis-url]

Concatenates a bunch of files into one new file (or into any writable stream you provide).

## Usage

`$ npm install stream-concat-files'

```javascript
var concatFiles = require('stream-concat-files');

// Just concatenate them into a file
concatFiles(['a.txt', 'b.txt', 'c.txt'], 'concat.txt', function (err) {
  if (err) throw err;

  // concat.txt is now saved!
});

// Pipe the concatenated result into an existing write stream
concatFiles(['a.txt', 'b.txt'], someWritableStream, function (err) {
  if (err) throw err;
  
  // someWritableStream has now been written to (and ended)!
  // (see options below for if you didn't want it to end your write stream)
});
```

## Options

You can optionally pass in an options object just before the callback.

- *`end`* – whether to end the write stream after the last file has been piped into it (default: `true`)

## Contributing

- run `mocha --watch` while you're working
- improvements welcome

## License
Copyright (c) 2014 . Licensed under the MIT license.
