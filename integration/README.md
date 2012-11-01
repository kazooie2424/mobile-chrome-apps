# Integration layer for Chrome Apps in Cordova

This directory contains the files used to wrap a Chrome app and make it run using Cordova.
Notes about the integration:

Files to use as templates (copy them and then change them):
* `background.js`: To be replaced with your app's background page. Remember to change its name in `manifest.json`. Have the background page `window.create` your own `index.html`, not `chromeapp.html`.
* `manifest.json`: Can be replaced with your app's manifest. Nothing special about Cordova here. Point it at the background page.
* Generate the API Javascript:
    * Go into the `api/` directory.
    * Run `grunt`. If you don't have Grunt installed, `sudo npm install -g grunt`.


Files that should not be edited (you should symlink these):
* `chromeapp.html`: **When you create your Cordova project, point it at this file, not `index.html`!**
* `chromebgpage.html`: More or less empty.
* `chromeappstyles.css`: Default CSS for Chrome Apps.
* `../api/dist/chromeapi.js`: Contains the chrome.\* implementations.
    * `../api/dist/chromeapi.min.js` as a minified alternative. If you want to use this one, change the filename in `chromeapp.html`.
* `cordova.android.js`: Required on Android.
* `cordova.ios.js`: Required on iOS.