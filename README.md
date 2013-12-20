SteedOS Apps PhoneGap Shell
===========

SteedOS Apps for Business is a cloud-based productivity suite that helps you and your team connect and get work done from anywhere on any device.   It's simple to setup, use and manage, allowing you to work smarter and focus on what really matters.

This project is initialized from PhoneGap 3.3.0 with following commands:

sudo npm install -g cordova
cordova create steedos-phonegap com.steedos.phonegap SteedOS-PhoneGap
cd steedos-phonegap
cordova platform add ios

cordova plugin add org.apache.cordova.inappbrowser
cordova plugin add org.apache.cordova.dialogs
cordova plugin add org.apache.cordova.vibration
cordova plugin add https://github.com/phonegap-build/PushPlugin.git
cordova plugin add org.apache.cordova.statusbar