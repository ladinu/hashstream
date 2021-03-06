# hashstream

This module hashes a readable stream

## Install
Using npm:
```sh
$ npm install hashstream
```
From source:
```sh
$ git clone https://github.com/ladinu/hashstream.git
$ cd hashstream/
$ npm link
```

## Examples

Get a SHA1 hash of example.com
```js
var hashStream = require('hashstream');

var example = request('http://example.com');
hashStream(example, function(err, hash) {
  if (!err) console.log("SHA1 hash of example.com: ", hash);
});
```

Get a md5 hash of google.com in base64
```js
var hashStream = require('hashstream');

var google  = require('http://google.com');
var options = { 'hash': 'md5', 'digest': 'base64' };

hashStream(google, options, function(err, hash) {
  if (!err) console.log("MD5 hash of google: ", hash);
});
```
## API

### hashstream(stream, [options], callback)

  * `stream` must be readable node stream 
  
  * `options` allow you to specefiy the hash type and digest encoding. By default
    `options` is set to the following: `{'hash': 'sha1', 'digest': 'hex'}`

  * `callback(err, hash)` will be called with an `error` and `hash` value when the given 
    stream end.



## Testing

```sh
$ cd hashstream/
$ npm install
$ npm test
```

## License

Copyright (c) 2013 Ladinu Chandrasinghe

Permission is hereby granted, free of charge, to any person obtaining a copy of this
software and associated documentation files (the "Software"), to deal in the Software
without restriction, including without limitation the rights to use, copy, modify,
merge, publish, distribute, sublicense, and/or sell copies of the Software, and to
permit persons to whom the Software is furnished to do so, subject to the following
conditions:

The above copyright notice and this permission notice shall be included in all copies
or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED,
INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A
PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT
HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF
CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR
THE USE OR OTHER DEALINGS IN THE SOFTWARE.
