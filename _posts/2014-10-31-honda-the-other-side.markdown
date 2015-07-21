---
layout: post
title:  The Other Side
slug: honda
client: Honda
date:   2014-10-31 00:00:00
tags: javascript film vanilla-javascript
excerpt: An interactive film with a twist, a dark-side story that mimics the light
role: Lead front-end developer
agency: Stinkdigital
---

Interactive video experience for Honda Civic Type R, allowing the user to watch a beautifully directed film with a twist - the whole film has been mimicked by the Civic Type R in a ‘dark side’ story that can be triggered by pressing the R button.

### YouTube landing screen

The site lives within a YouTube gadget on a bunch of Honda’s global channels - it’s disguised as a normal player so the user is genuinely surprised and delighted when they find out they can interact with the film.

### Video experience

### Video while pressing and holding the 'R’ key

### Video ending

Both worlds meet at the end of the film, and both the Civic and Civic Type R can be seen parked by each-other.

### Interactive slider

A smooth dragging motion allows the user to explore both sides of the Civic, and hopefully replay the film to see what they might have missed the first time round.

### The tech side

On desktop, the site lives within a YouTube gadget, which is essentially an iframe that’s included in place of the usual video content in a YouTube channel. We swap out one of the 2 videos (which are incidentally hosted on YouTube) depending on whether the viewer’s pressing R or not.

On tablet we have a single video (hosted separately) that is double width and has both films side-by-side. When it comes to swap the film we simply shift the video left or right. The audio has to be loaded before the film can be downloaded as only a single piece of media can be downloaded at once on iOS devices, as such we’ve used a single audio file too. To achieve the separate soundtracks for each film, we used the left and right channels that make up stereo sound and use each one exclusively to hold the audio for the different films. These are toggled in sync with the films.

The mobile experience is simply a teaser video, however we created some prototypes for an image-sequence version which wasn’t carried through to production in the end.

See the film here: hondatheotherside.com and remember to press 'R’!
