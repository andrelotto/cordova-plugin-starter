# Cordova Starter Plugin

After experiencing a LOT of pain getting cordova up and running with a sample plugin, I decided to make this repo.
For issues I experienced, please refer to [common-issues](common-issues.md).

## Using

Create a new Cordova Project

    $ cordova create starter com.example.myapp MyApp

Install the plugin

    $ cd MyApp
    $ cordova plugin add https://github.com/thiagodebastos/cordova-plugin-starter.git

Alternatively, you can work locally by creating a symlink between `<PROJECT_DIR>/plugins` and your plugin dir with the [`--link` flag](https://cordova.apache.org/docs/en/latest/reference/cordova-cli/#cordova-plugin-command).

    $ cordova plugin add --link <PATH_TO_PLUGIN_DIR>/cordova-plugin-starter --save


Edit `www/js/index.js` and add the following code inside `onDeviceReady`

```js
    var success = function(message) {
        alert(message);
    }

    var failure = function() {
        alert("Error calling Starter Plugin");
    }

    starter.greet("World", success, failure);
```

Install iOS or Android platform

    cordova platform add ios
    cordova platform add android

Run the code

    cordova run

Or locally:

    cordova emulate <android|ios>

## More Info

For more information on setting up Cordova see [the documentation](http://cordova.apache.org/docs/en/latest/guide/cli/index.html)

For more info on plugins see the [Plugin Development Guide](http://cordova.apache.org/docs/en/latest/guide/hybrid/plugins/index.html)
