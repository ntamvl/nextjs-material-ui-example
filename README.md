# Next.js 2 with Material-UI Example

## Init node project
```
npm init -y
npm i -S next react react-dom material-ui react-tap-event-plugin
```

## Add script to `package.json`
```json
"scripts": {
  "dev": "next",
  "build": "next build",
  "start": "next start",
  "test": "echo \"Error: no test specified\" && exit 1"
}
```

## Create index page
```
mkdir pages && cd pages
touch index.js
```

with content in file `index.js`
```javascript
import React                from 'react';
import Head                 from 'next/head';
import injectTapEventPlugin from 'react-tap-event-plugin';
import MuiThemeProvider     from 'material-ui/styles/MuiThemeProvider';
import getMuiTheme          from 'material-ui/styles/getMuiTheme';
import AppBar               from 'material-ui/AppBar';

try { injectTapEventPlugin(); } catch (e) {  }

const muiTheme = getMuiTheme({ userAgent: false });

export default class extends React.Component {
  render() {
    return (
      <MuiThemeProvider muiTheme={muiTheme}>
        <div>
          <Head>
            <title>Next.js 2 with Material-UI Example</title>
            <meta name="viewport" content="initial-scale=1.0, width=device-width"/>
          </Head>

          <AppBar
            title="Page Title"
            iconClassNameRight="muidocs-icon-navigation-expand-more"
          />

          <h1>Page content</h1>
          <p>Next.js 2 with Material-UI Example</p>

        </div>
      </MuiThemeProvider>
    )
  }
}
```

## Run Next.js app
```
npm run dev
```

Enjoy :D
