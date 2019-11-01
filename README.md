# md5-file-graceful

Get the MD5-sum of a given file, with low memory usage, even on huge files.

Open file with [graceful-fs](https://github.com/isaacs/node-graceful-fs)

## Installation

```sh
npm install --save md5-file-graceful
```

## Usage

### As a module
```js
const md5File = require('md5-file-graceful')

/* Async usage */
md5File('LICENSE.md', (err, hash) => {
  if (err) throw err

  console.log(`The MD5 sum of LICENSE.md is: ${hash}`)
})

/* Sync usage */
const hash = md5File.sync('LICENSE.md')
console.log(`The MD5 sum of LICENSE.md is: ${hash}`)
```

### As a command line tool
```
$ md5-file-graceful LICENSE.md
```

## Promise support

If you require `md5-file-graceful/promise` you'll receive an alternative API where all
functions that takes callbacks are replaced by `Promise`-returning functions.

```js
const md5File = require('md5-file-graceful/promise')

md5File('LICENSE.md').then(hash => {
  console.log(`The MD5 sum of LICENSE.md is: ${hash}`)
})
```

## API

### `md5File(filepath: string, cb: function)`

Asynchronously get the MD5-sum of the file at `filepath`.

The callback `cb` will be called with `(err: Error, hash: string)`.

### `md5File.sync(filepath: string) => string`

Synchronously get the MD5-sum of the file at `filepath`.

### License

MIT
