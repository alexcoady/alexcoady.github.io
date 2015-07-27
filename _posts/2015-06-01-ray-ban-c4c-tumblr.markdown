---
layout: post
title: "&#35;Campaign4Change Tumblr"
slug: rayban-c4c
project_url: http://ray-ban.tumblr.com/c4c
client: Ray-Ban
date: 2015-06-01 00:00:00
tags: javascript backbone canvas tumblr
excerpt: "Tear you way through Tumblr to find your &#35;Campaign4Change"
role: Lead front-end developer
agency:
  name: Stinkdigital
  url: http://stinkdigital.com
---

Ray-Ban's &#35;Campaign4Change Tumblr is an interactive micro-site that lets users tear through a series of images and messaging until they find a phrase that represents their *campaign for change*.

The bottom or the top image can be torn away to reveal a new message:

![Before tearing]({{ "/sample.jpg" | prepend: page.slug | prepend: page.imagesrc | prepend: site.baseurl }})

Users can continue to tear until they find a message they agree with:

![Tearing]({{ "/tear.jpg" | prepend: page.slug | prepend: page.imagesrc | prepend: site.baseurl }})

When the user finds one they like, they can share it on download the file to their computer:

![Sharing on facebook]({{ "/facebook.jpg" | prepend: page.slug | prepend: page.imagesrc | prepend: site.baseurl }})

### The tech side

The experience is created using 3 `<canvas>` elements:

1. Shows the current layer being torn away
1. Shows the cumulative image generated so far
1. Used to merge the layers and export the image for sharing

When the user decides to share an image, the canvas is rasterised and a new window is opened. The new window submits a form that contains the image, and the form is triggered to send the image to the server.

Once the server has parsed the image as the correct format, it redirects the user to appropriate URL for sharing, with the image and site url populated already.

If the user has chosen to download the image instead of share, the form is submitted from the current window and the download happens on the page/tab the user is currently on.
