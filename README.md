## react-brunch
Adds [React](http://facebook.github.io/react) support to [brunch](http://brunch.io)
by automatically compiling `*.jsx` files.

### Optional

You can configure react-brunch to automatically insert a react header 
(`/** @jsx React.DOM */`) into all `*.jsx` files. Disabled by default. 

Example `config.coffee`:

```coffeescript
exports.config =
  plugins:
    react:
      autoIncludeCommentBlock: yes
  
  # Usual brunch config stuf...
  files:
    javascripts:
      joinTo: 'app.js'
    stylesheets:
      joinTo: 'app.css'
    templates:
      joinTo: 'app.js'
```

### Notes

react-brunch only supports compiling `*.jsx` files. It doesn't peek at `*.js` to
see if they have the React-ify comment header. I doubt it ever will. Here's why:

Any `.js` file should be browser loadable. Embedding JSX will break in any JS
environment. Therefore, I chose to have react-brunch only pre-processes `.jsx`
files.

## Usage
Install the plugin via npm with `npm install --save react-brunch`.

Or, do manual install:

* Add `"react-brunch": "x.y.z"` to `package.json` of your brunch app.
  Pick a plugin version that corresponds to your minor (y) brunch version.
* If you want to use git version of plugin, add
`"react-brunch": "git+ssh://git@github.com:brunch/react-brunch.git"`.

## Credit

This is based on Paul Miller's [javascript-brunch](https://github.com/brunch/javascript-brunch)
project and adjusted to compile React (.jsx) files.

## License

The MIT License (MIT)

Copyright (c) 2013 Matt McCray

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN
THE SOFTWARE.
