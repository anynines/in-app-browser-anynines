<a style="float:right;font-size:12px;" href="http://github.com/ionic-team/ionic-native/edit/master/src/@ionic-native/plugins/in-app-browser/index.ts#L250">
  Improve this doc
</a>

# In App Browser

## Installation

This is an extended fork of the original plugin that adds som features
- support for custom headers (e.g. auth) in the inital web location request
- params for position and size in the InAppBrowserOptions
- a public goBack() method that can be called from the Ionic app

It is supposed to be used with the forked cordova-plugin-inappbrowser-anynines

```
$ npm i cordova-plugin-inappbrowser-anynines@https://github.com/anynines/cordova-plugin-inappbrowser-anynines.git
$ npm install @ionic-native/in-app-browser@https://github.com/anynines/in-app-browser-anynines.git
```

## [Usage Documentation](https://ionicframework.com/docs/native/in-app-browser/)

Plugin Repo: [https://github.com/apache/cordova-plugin-inappbrowser](https://github.com/apache/cordova-plugin-inappbrowser)

Launches in app Browser

## Supported platforms

- AmazonFire OS
  - Android
  - Browser
  - iOS
  - macOS
  - Windows
  


