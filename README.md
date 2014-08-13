commist
=======

Build command line application with multiple commands the easy way.
Built on minimist.

```js
var program = require('commist')()
  , result

result = program
  .register('abcd', function(args) {
    console.log('just do', args)
  })
  .register('abcde code', function(args) {
    console.log('doing something', args)
  })
  .register('another command', function(args) {
    console.log('anothering', args)
  })
  .parse(process.argv.splice(2))

if (result) {
  console.log('no command called, args', result)
}
```

When calling _commist_ programs, you can abbreviate down to three char
words. In the above example, these are valid commands:

```
node example.js abc
node example.js abc cod
node example.js anot comm
```

Moreover, little spelling mistakes are corrected too:

```
node example.js abcs cod
```

Acknowledgements
----------------

This project was kindly sponsored by [nearForm](http://nearform.com).

License
-------

MIT
