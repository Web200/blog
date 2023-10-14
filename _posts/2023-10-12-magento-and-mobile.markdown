---
layout: post
title:  "Magento and Mobile"
date:   2023-10-12 20:42:02 +0200
categories: magento pwa hyva turbo 
---
Magento currently allows building a website "simply".  
When we look at the mobile side, we currently have several solutions:

#### Having a mobile theme available on a phone's web browsers.
The Luma / [Hyva](https://www.hyva.io/){:target="_blank"} theme has a native version adapted for mobile.

#### Having a PWA version.

* ###### [PWA Studio](https://github.com/magento/pwa-studio){:target="_blank"}
  * Magento's official toolkit for building PWA frontends.
  * Tech stack : React, Redux, and GraphQL.
  * **994** sites (list from [BuiltWith](https://trends.builtwith.com/shop/Magento-PWA-Studio){:target="_blank"})
  * Discontinued ? (See Mark Shust reflection on [Twitter](https://twitter.com/MarkShust/status/1705054087169876312){:target="_blank"})
* ###### [ScandiPWA](https://github.com/scandipwa/scandipwa){:target="_blank"}
  * An independent PWA solution for Magento 2.
  * Tech stack : React, Redux, and GraphQL.
  * **314** sites (list from [BuiltWith](https://trends.builtwith.com/framework/ScandiPWA){:target="_blank"})
* ###### [Vue Storefront 2](https://github.com/vuestorefront/magento2){:target="_blank"}
  * PWA frontend platform for e-commerce with a Magento 2 connector
  * Tech stack : Vue.js, Nuxt.js, and GraphQL.
  * **352** sites (list from [BuiltWith](https://trends.builtwith.com/shop/Vue-Storefront-2){:target="_blank"})
 
#### Build a PWA version.

 * You can build your own PWA version from scratch.
 * You can choose the tech stack you want, but you will have to build everything from scratch.

#### Build a native application.

 * You will need a team that is proficient in Swift (iOS) and Kotlin (Android) to create two different applications.
 * For all data exchanges, you will need to use the GraphQL endpoints available in Magento, or even create new ones for specific needs.
 Currently, Magento does not cover 100% of the requirements for an application with its GraphQL API.

#### Having a React Native application.

 * You will need a team proficient in React Native and with some knowledge of iOS/Android builds to create an application.
 * For all data exchanges, you will need to use the GraphQL endpoints available in Magento, or even create new ones for specific needs.
  Currently, Magento does not cover 100% of the needs for an application with its GraphQL API.

### Having a Turbo Native App

 * You keep your native web theme, and you just need to build the iOS/Android application.
 * No need to build and publish a version on the App Store/Play Store with every change, as it's your website that's integrated into the application's webview.
 * Turbo Native App showcase available here : [turbonative.directory](https://turbonative.directory/){:target="_blank"}


## Next step : How to use Turbo with Magento Easily ?
