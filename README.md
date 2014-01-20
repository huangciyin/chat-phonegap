SteedOS Apps PhoneGap Shell
===========

SteedOS Apps for Business is a cloud-based productivity suite that helps you and your team connect and get work done from anywhere on any device.   It's simple to setup, use and manage, allowing you to work smarter and focus on what really matters.

This project is initialized from PhoneGap 3.3.0 with following commands:

export PATH=${PATH}:~/svn/sdk/platform-tools:~/svn/sdk/tools

source ~/.bash_profile

sudo npm install -g cordova

cordova create chat-phonegap com.steedos.chat Chat

cd chat-phonegap

cordova plugin add org.apache.cordova.inappbrowser

cordova plugin add org.apache.cordova.dialogs

cordova plugin add org.apache.cordova.vibration

cordova plugin add https://github.com/phonegap-build/PushPlugin.git

cordova plugin add org.apache.cordova.statusbar

cordova plugin add https://github.com/VitaliiBlagodir/cordova-plugin-datepicker

cordova plugin add org.apache.cordova.statusbar

cordova plugin add org.apache.cordova.splashscreen

brew update

brew install ant

=============

Build for android: 

export PATH=${PATH}:~/svn/sdk/platform-tools:~/svn/sdk/tools

md platforms

cordova platform remove android

cordova platform add android

open www/config.xml, change versionName

open platforms/android/AndroidManifest.xml,open platforms/android/AndroidManifest.xml, change versionCode 

cordova build android --release

mkdir dist 

# Sign
jarsigner -verbose -keystore ../steedos-certs/android/android.keystore -signedjar dist/SteedOS_Chat_signed.apk platforms/android/bin/Chat-release-unsigned.apk android

# Optimize
rm dist/SteedOS_Chat_1.1.0.apk
zipalign -v 4 dist/SteedOS_Chat_signed.apk dist/SteedOS_Chat_1.1.0.apk
