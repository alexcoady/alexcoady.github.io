---
layout: post
title: The Other Side
slug: honda
client: Honda
date: 2014-10-31 00:00:00
tags: javascript film vanilla-javascript
excerpt: An interactive film with a twist, a dark-side story that mimics the light
role: Lead front-end developer
agency:
  name: Stinkdigital
  url: http://stinkdigital.com
---

Interactive video experience for Honda Civic Type R, allowing the user to watch a beautifully directed film with a twist - the whole film has been mimicked by the Civic Type R in a *dark side* story that can be triggered by pressing the R button.

### The tech side

On desktop, the site lives within a YouTube gadget, which is essentially an iframe that’s included in place of the usual video content in a YouTube channel. We swap out one of the 2 videos (which are incidentally hosted on YouTube) depending on whether the viewer’s pressing R or not.

On tablet we have a single video (hosted separately) that is double width and has both films side-by-side. When it comes to swap the film we simply shift the video left or right. The audio has to be loaded before the film can be downloaded as only a single piece of media can be downloaded at once on iOS devices, as such we’ve used a single audio file too. To achieve the separate soundtracks for each film, we used the left and right channels that make up stereo sound and use each one exclusively to hold the audio for the different films. These are toggled in sync with the films:

{% highlight javascript %}
Audio.p.setTrack = function ( id ) {

  if ( id === DARK_SIDE ) {
    this.GAIN_LEFT.gain.value = this.volume;
    this.GAIN_RIGHT.gain.value = 0;
  } else {
    this.GAIN_LEFT.gain.value = 0;
    this.GAIN_RIGHT.gain.value = this.volume;
  }
};
{% endhighlight %}

For mobile devices, we opted to show a teaser video as, at the time, we were unable to play a video on iOS without using the native video player, which wouldn't let us swap videos when needed or place a button on top for the **Press R** interaction. We worked on a number of prototypes for image-sequence versions but they weren't good enough to put to production.

More recently, we discovered a way to achieve the same effect on mobile as we have on desktop, using a hack where we never trigger a video element's `.play()` method, but instead just loop through the frames manually; however the campaign had already ended so our prototype for this never made the production site either.

See the film here: [hondatheotherside.com](http://hondatheotherside.com) and remember to **press R**.
