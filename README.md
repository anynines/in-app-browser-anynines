<a style="float:right;font-size:12px;" href="http://github.com/ionic-team/ionic-native/edit/master/src/@ionic-native/plugins/in-app-browser/index.ts#L250">
  Improve this doc
</a>

# In App Browser

This is an extended fork of the original Ionic Native InAppBrowser plugin that adds the following features:
- support for custom headers (e.g. auth) in the inital web location request
- params for position and size in the InAppBrowserOptions
- a public goBack() method that can be called from the Ionic app to step back in the browser history

It is supposed to be used with the forked cordova-plugin-inappbrowser-anynines

## Installation

```
$ npm i cordova-plugin-inappbrowser-anynines@https://github.com/anynines/cordova-plugin-inappbrowser-anynines.git
$ npm install @ionic-native/in-app-browser-anynines@https://github.com/anynines/in-app-browser-anynines.git
```

## [Usage Documentation](https://ionicframework.com/docs/native/in-app-browser/)

For all regular features and instuctions see Ionic's original repo:

Plugin Repo: [https://github.com/apache/cordova-plugin-inappbrowser](https://github.com/apache/cordova-plugin-inappbrowser)

Launches in app Browser


## Simple example implementation

```typescript
import React from 'react'
import './WebView.css' 
import { InAppBrowser, InAppBrowserObject, InAppBrowserOptions } from '@ionic-native/in-app-browser-anynines'

export const WebView: React.FC = (props) => {

  type InAppBrowserInstance = InAppBrowserObject | null

  const [webView, setWebView] = React.useState(null as InAppBrowserInstance)

  const onBackButton = () => {
    debugger
    console.log('back', webView)
    if (webView) {
      (webView as unknown as InAppBrowserObject).goBack()
    }
  }

  React.useEffect(() => {

    const url = 'https://<MyAuthenticatedWebLocation>'

    const browserOptions: InAppBrowserOptions = {
      location: 'no',
      toolbar: 'no',
      x: 0,
      y: 78, // calculate what space you need for header, nav etc.
      width: window.innerWidth,
      height: window.innerHeight - 78
    }

    const headers = {
      'Authorization': 'Bearer abcd123456789<MyAuthToken>'
    }

    const browser = InAppBrowser.create(url, '_blank', browserOptions, headers)
    setWebView(browser)

  }, [])

  return (
    <div className='webview'>
      <button onClick={onBackButton}>Back</button>
    </div>
  )

}
```

## Supported platforms

- Android
- iOS

The additions above were only implemented in these while the original plugin supports a broader platform range.
  


