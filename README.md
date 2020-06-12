# Develop themes for liform

This package contains the required dependencies and files for developing themes for [Liform React Final](https://github.com/ph-fritsche/liform-react-final)

## Usage

#### Install via [Yarn](https://yarnpkg.com/getting-started/install) in your theme repository
```
yarn add --dev https://github.com/ph-fritsche/liform-theme-dev
```

#### Let your `webpack.config.js` provide the default config
```js
const conf = require('liform-theme-dev/webpack.config')
module.exports = conf
```

#### Set up a simple `index.html`
```html
<html>
    <body>
        <div id="liform"></div>
        <script src="/build/liform.js"></script>
    </body>
</html>
```

#### Download the reference props for Symfony's built in types
```
curl -o props.json https://ph-fritsche.github.io/liform/build/SymfonyFormType.json
```

#### Set up a `liform.jsx` that includes your theme and renders the component
```jsx
import React from 'react'
import ReactDOM from 'react-dom'
import Liform from 'liform-react-final'

import MyAwesomeTheme from './src'

// you can set it as default or provide it via 'theme' prop
Liform.defaultTheme = MyAwesomeTheme

import props from './props.json'

ReactDOM.render(
  <Liform {...props} name='form'/>,
  document.getElementById('liform')
)
```

#### Serve and inspect your theme in the browser
```
yarn webpack-dev-server
```
