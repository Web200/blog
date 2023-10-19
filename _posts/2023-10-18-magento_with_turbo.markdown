---
layout: post
title:  "Magento & Turbo"
date:   2023-10-18 20:42:02 +0200
categories: magento turbo 
---

The first step to having a native application with [Turbo Android](https://github.com/hotwired/turbo-android) / [Turbo iOS](https://github.com/hotwired/turbo-ios) is to have a Magento that works with Turbo.
To start with an up-to-date Magento theme, I decided to use Hyva.

Creating a Module and a Theme

1 - Load the Turbo library

```
<script type="module" src="<?= $block->getViewFileUrl('js/turbo.js')?>"></script>
```

2 - Map page load events to Turbo's functionality

On default behavior, when a page is loaded, some Alpine components are reloaded.
With Turbo, there's only one page load. After that, each page is called via xhr and the DOM is modified accordingly.

```
document.documentElement.addEventListener("turbo:render", function(event) {
    window.dispatchEvent(new CustomEvent("alpine:initialized"));
    window.dispatchEvent(new CustomEvent("DOMContentLoaded"));
});
```

3 - Update some JavaScript calls

Form submissions should go through Turbo-specific calls.

```
//$form.submit();
Turbo.navigator.submitForm($form);

//window.location.href = ...
Turbo.visit(...);
```

4 - Hide some blocks in the application

On the native application, if you want to hide specific blocks, just use the "hideOnWebview" argument.

Example: If I want to hide the website's logo:

```
<referenceBlock name="logo">
    <arguments>
        <argument name="hideOnWebview" xsi:type="boolean">true</argument>
    </arguments>
</referenceBlock>
```

5 - Wait loading of a previously visited page or display it directly ?

Use the no-preview directive to specify that a cached version of the page should not be shown as a preview during an application visit. Pages marked no-preview will only be used for restoration visits.

To specify that a page should not be cached at all, use the no-cache directive. Pages marked no-cache will always be fetched over the network, including during restoration visits.

```
<head>
  <meta name="turbo-cache-control" content="no-cache">
</head>
```


Preview of turbo navigation in chrome :


To simplify the installation, the easiest way is to install the [Web200_Turbo](*) module.

