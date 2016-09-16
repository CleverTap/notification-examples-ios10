# iOS 10 Rich Push Notification Example Projects

![push1](https://github.com/CleverTap/notification-examples-ios10/blob/master/images/push1a.PNG)
![push2](https://github.com/CleverTap/notification-examples-ios10/blob/master/images/push2a.PNG)

Rich push notifications are enabled in iOS 10 via a [Notification Service Extension](https://developer.apple.com/reference/usernotifications/unnotificationserviceextension), a separate and distinct binary embedded in your app bundle.

Be sure to enable push notifications in your main app in the normal way.

Then, to create a Notification Service Extension, create a new target in your project and select Notification Service Extension.

![notification service extension](https://github.com/CleverTap/notification-examples-ios10/blob/master/images/service_extension.png)

Then, when sending notifications via APNS:
- include the mutable-content flag in your aps payload (this key must be present in the aps payload or the system will not call your app extension) 
- add custom key:value pair(s) to the payload with the necessary data to construct the download url for the media you want to display (your app extension code will then read these key-value pairs to initiate the media download on the device).  Apple supports images, video, audio and gif.

When using the CleverTap Dashboard to send push, select Advanced, set the mutable-content flag check box and add your key:value pair(s).

![clevertap dashboard](https://github.com/CleverTap/notification-examples-ios10/blob/master/images/dashboard.png)

See [an example Swift project here](https://github.com/CleverTap/notification-examples-ios10/blob/master/notif10swift/NotificationService/NotificationService.swift).

See [an example Objective-C project here](https://github.com/CleverTap/notification-examples-ios10/blob/master/notif10objc/NotificationService/NotificationService.m).

