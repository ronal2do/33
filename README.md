# DOCUMENTATION:
Please read the documentation here: http://bit.ly/1aKm23w




Your Ionic project is ready to go! Some quick tips:

* cd into your project:
```
cd ionwordpress
```

* Setup this project to use Sass:
```
ionic setup sass
```

* Develop in the browser with live reload:
```
ionic serve
```

* Add a platform (ios or Android):
```
ionic platform add ios [android]
```

Note: iOS development requires OS X currently
See the Android Platform Guide for full Android installation instructions:
https://cordova.apache.org/docs/en/edge/guide_platforms_android_index.md.html

* Build your app:
```
ionic build <PLATFORM>
```

* Simulate your app:
```
ionic emulate <PLATFORM>
```

* Run your app on a device:
```
ionic run <PLATFORM>
```

* Package an app using Ionic package service:
```
ionic package <MODE> <PLATFORM>
```

* Generate icon and splash screen:
```
ionic resources
```

For more help use ```ionic --help``` or visit the Ionic docs: http://ionicframework.com/docs

* If you build for ios and find yourself having cordova plugin errors (like iOS unable to find plugins) do the following:

1. delete ./plugins/ios.json
2. then delete ./platforms/ios
3. run ionic platform add ios
4. ionic build ios.
Deleting ios.json helps to force it to recompile the plugins.



### To prepare the apk to upload to Google Play (see: http://ionicframework.com/docs/guide/publishing.html)
#### 1)
```
cordova build --release android
```
#### 2)
```
keytool -genkey -v -keystore 33app-key.keystore -alias 33app -keyalg RSA -keysize 2048 -validity 10000
```



#### 3)
```
jarsigner -verbose -sigalg SHA1withRSA -digestalg SHA1 -keystore my-release-key.keystore android-release-unsigned.apk alias_name
```
#### 4)
```
zipalign -v 4 android-release-unsigned.apk 33club.apk
```


* Run the following commands to install the cordova plugins used by the app:

 <!-- We'll include the Barcode plugin as an example -->
    <gap:plugin name="com.phonegap.plugins.barcodescanner" />


phonegap plugin add org.apache.cordova.device
ionic plugin add org.apache.cordova.console
ionic plugin add com.ionic.keyboard
ionic plugin add org.pushandplay.cordova.apprate
ionic plugin add org.apache.cordova.inappbrowser
ionic plugin add com.google.cordova.admob
ionic plugin add com.rjfun.cordova.iad
ionic plugin add org.apache.cordova.dialogs
ionic plugin add org.apache.cordova.globalization
ionic plugin add https://github.com/katzer/cordova-plugin-email-composer.git
ionic plugin add nl.x-services.plugins.socialsharing
ionic plugin add com.google.playservices
