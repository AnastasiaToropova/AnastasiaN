# Web Push notifications in Firefox

Web Push allows websites to notify users of new messages or updated content. While Firefox is open, websites who have been granted permissions can send notifications to your browser and display them on the screen. Users can easily allow or disable notifications and control how these notifications appear. 

![](https://user-media-prod-cdn.itsre-sumo.mozilla.net/uploads/gallery/images/2017-10-18-05-45-38-20e1d7.png)

**Table of Contents**

- [Upgraded Notifications](https://github.com/AnastasiaToropova/AnastasiaN/edit/master/README.md "Upgraded Notifications")
- [What is Web Push?](https://github.com/AnastasiaToropova/AnastasiaN/edit/master/README.md "What is Web Push?")
- [How does it work?](https://github.com/AnastasiaToropova/AnastasiaN/edit/master/README.md "How does it work?")
- [What information do I share with a website?](https://github.com/AnastasiaToropova/AnastasiaN/edit/master/README.md "What information do I share with a website?")
- [What information does Firefox use to provide Web Push?](https://github.com/AnastasiaToropova/AnastasiaN/edit/master/README.md "What information does Firefox use to provide Web Push?")
- [How do I revoke Web Push permissions for a specific site?](https://github.com/AnastasiaToropova/AnastasiaN/edit/master/README.md "How do I revoke Web Push permissions for a specific site?")
- [How do I add Web Push to my website?](https://github.com/AnastasiaToropova/AnastasiaN/edit/master/README.md "How do I add Web Push to my website?")
- [How do I stop Firefox asking me to allow notifications?](https://github.com/AnastasiaToropova/AnastasiaN/edit/master/README.md "How do I stop Firefox asking me to allow notifications?")

## Upgraded Notifications

Firefox can deliver on-screen notifications even when that site isn’t loaded. Using the Push API, a [W3C standard](https://www.w3.org/TR/push-api/), Firefox receives a push message and can show notifications (if permitted by the user) at any time. Sites can also use Push to update data in the background even without showing you a notification. If you already gave permission to a site to send notifications, the site will also be able to use the Push API. You can choose whether or not to give permission for a specific website by following these instructions: 

1. Click the ![](https://user-media-prod-cdn.itsre-sumo.mozilla.net/uploads/gallery/images/2016-02-25-12-29-33-78136e.png) icon to bring up the [Control Center](https://support.mozilla.org/en-US/kb/control-center-site-privacy-and-security-firefox);

2. Click the button in the right connor of the the Permissions tab.
![](http://5o.f.mf-image.ru/d/eyJ0IjoiMjAxOS0wNy0yOVQxNTowOToyMy4wNjg3ODM2WiIsInRtIjoxNSwiYmQiOjEsImZkIjo1ODg3NDMxLCJyZiI6bnVsbCwic2wiOjAsImZuIjpudWxsLCJyIjoiaHR0cHM6Ly9teS1maWxlcy5ydS81ZTVzaHAiLCJsIjpudWxsfQ,,.23614028C46610B1137750B7774EB394./2222.png)

3. Check the box if you do not want to receive notifications until Firefox restarts. Otherwise, uncheck the box.

![](http://a1.f.mf-image.ru/d/eyJ0IjoiMjAxOS0wNy0yOVQxNTo0NDoyNC44MDUxNDYzWiIsInRtIjoxNSwiYmQiOjEsImZkIjo1ODg3NDM0LCJyZiI6bnVsbCwic2wiOjAsImZuIjpudWxsLCJyIjoiaHR0cHM6Ly9teS1maWxlcy5ydS9qeWptNXgiLCJsIjpudWxsfQ,,.1BA3759115CEF724780AD8674BC72156./3333.png)


## What is Web Push?

Web Push is an optional feature that allows websites to send you messages even when the site isn’t loaded. Sites can use this feature to provide you with notifications or update data in the background.

For instance, you can subscribe to notifications from your favorite shopping websites which can notify you of new promotions or offers. You can subscribe to notifications from different websites. A concert site may offer you notifications for shows of your favorite band; you allow that site to notify you, and a week later you get a notification that your band is on tour.

You will only receive messages from sites for which you have granted permission.

## How does it work?

Websites can install a [Service Worker](https://developer.mozilla.org/ru/docs/Web/API/Service_Worker_API), a background web page with a limited set of functionality, that can subscribe to the push service. The website can then send a push message through Mozilla’s Web Push service to your browser, which can process that message and display a notification on your screen.

![](https://user-media-prod-cdn.itsre-sumo.mozilla.net/uploads/gallery/images/2016-01-22-13-08-43-059641.png)

Clicking the notification can open a website or switch to that site’s tab if loaded.

## What information do I share with a website?

A website that has been granted permissions can send you push messages when the site isn’t loaded. A quota limits the number of push messages without an on-screen notification that sites can send you. Websites that exceed the quota will have its push messaging disabled and the user must revisit the website again to resubscribe. Web Push does not directly allow websites to determine your IP address.

## What information does Firefox use to provide Web Push?

Firefox maintains an active connection to a push service in order to receive push messages as long as it is open. The connection ends when Firefox is closed. On our server we store a randomized identifier for your browser, along with a randomized identifier for each site you authorize.

On Firefox for desktop, the push service is operated by Mozilla. Firefox for Android uses a combination of the Mozilla Web Push service and Google’s Cloud Messaging platform to deliver notifications to Firefox for Android.

In both cases, push messages are encrypted per the [IETF spec](https://tools.ietf.org/html/rfc8030) and only your copy of Firefox can decipher them. The encrypted messages are stored on the server until they are delivered or expire.

 ## How do I revoke Web Push permissions for a specific site?
 
 Web Push is always opt-in in Firefox. A site cannot send you push messages without your permission. To stop a specific site from sending you push messages:
 
1. Click the menu button ![](https://user-media-prod-cdn.itsre-sumo.mozilla.net/uploads/gallery/images/2017-10-22-15-37-15-18c775.png) and choose **Options**.

![](http://8g.f.mf-image.ru/d/eyJ0IjoiMjAxOS0wNy0yOVQxNTo0MDoyNi44MDM1MTM0WiIsInRtIjoxNSwiYmQiOjEsImZkIjo1ODg3NDUxLCJyZiI6bnVsbCwic2wiOjAsImZuIjpudWxsLCJyIjoiaHR0cHM6Ly9teS1maWxlcy5ydS9vbGJzOWEiLCJsIjpudWxsfQ,,.825F01B0A9C6229A17F4FAAB3459A56B./4.png)

2. Select the *Privacy & Security* panel and go down to the *Permissions* section.

3. Click the **Settings…** button next to *Notifications*.

![](http://lr.f.mf-image.ru/d/eyJ0IjoiMjAxOS0wNy0yOVQxNTo0OToyOC4wNzU1MTA3WiIsInRtIjoxNSwiYmQiOjEsImZkIjo1ODg3NDYzLCJyZiI6bnVsbCwic2wiOjAsImZuIjpudWxsLCJyIjoiaHR0cHM6Ly9teS1maWxlcy5ydS9mZ3JheTAiLCJsIjpudWxsfQ,,.DA2588ABFCD22F008DE25F51263E1109./5.png)
4. Select the website.

5. Click the button **Remove Website**

To stop all sites from sending you push messages, follow the above steps except, instead of selecting a specific site, click **Remove All Websites**. Websites will not be able to send you messages and will need to ask your permission to send them in the future.

|**To stop notifications on a specific webpage (requires a page reload):** Click the ![](https://user-media-prod-cdn.itsre-sumo.mozilla.net/uploads/gallery/images/2016-02-25-12-29-33-78136e.png) icon to bring up the [Control Center](https://support.mozilla.org/en-US/kb/control-center-site-privacy-and-security-firefox), find the *Send Notifications* permission and click the **x** next to *Allowed* to remove the permission.|
|----------------------------------------------------------------------------------------------------------------------|

## How do I add Web Push to my website?

The [Push API specification](https://developer.mozilla.org/docs/Web/API/Push_API) explains how to create a Service Worker and send push messages.

## How do I stop Firefox asking me to allow notifications? 

If a site indicates to Firefox that it wants to show notifications, by default, Firefox asks whether you want to grant permission. You can set Firefox to automatically deny permission without asking. Even after the change, you can make exceptions for sites *you want* to show notifications or use push features.
1. Click the menu button ![](https://user-media-prod-cdn.itsre-sumo.mozilla.net/uploads/gallery/images/2017-10-22-15-37-15-18c775.png) and choose *Options*.
2. Select the *Privacy & Security* panel and scroll down to the *Permissions* section.
Click the **Settings…** button to the right of Notifications.

![](https://user-media-prod-cdn.itsre-sumo.mozilla.net/uploads/gallery/images/2018-04-09-09-06-49-fc7acb.png)

4. Check the box for *Block new requests asking to allow notifications* and then click **Save Changes**.
              
              
