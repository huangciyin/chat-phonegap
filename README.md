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

cordova plugin add org.apache.cordova.file

cordova plugin add org.apache.cordova.geolocation

brew update

brew install ant

=============

Build for android: 

打开目录 www/config.xml,修改widget的属性"version"和"versionCode"，例如，如果之前的版本名是1.4.0，新版本名就应该加0.1变成1.5.0，应该修改成[version="1.5.0" versionCode="150"]

export PATH=${PATH}:~/svn/sdk/platform-tools:~/svn/sdk/tools

md platforms

cordova platform remove android

cordova platform add android

打开目录 platforms/android/AndroidManifest.xml，修改manifest的属性"android:versionCode",例如， 如果之前的版本名是1.4.0，新版本名就应该加0.1变成1.5.0，应该修改成[android:versionCode="150"]

把app的名称为icon.png及screen.9.png(九宫图)图片copy到目录platforms/android/res/drawable-*/中
把app的icon.png及screen.9.png图片copy到目录platforms/android/res/drawable-*/中

cordova build android --release

mkdir dist 

# Sign
jarsigner -verbose -keystore ../steedos-certs/android/android.keystore -signedjar dist/SteedOS_Chat_signed.apk platforms/android/ant-build/Chat-release-unsigned.apk android

# Optimize
rm dist/SteedOS_Chat_1.5.apk
zipalign -v 4 dist/SteedOS_Chat_signed.apk dist/SteedOS_Chat_1.5.apk
