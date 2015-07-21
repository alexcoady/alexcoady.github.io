---
layout: post
title:  Website redesign
slug: stink
client: Stink films
date: 2015-03-15 00:00:00
tags: javascript film backbone
excerpt: Building the new home of Stink
role: Lead front-end developer
agency: Stinkdigital
---
[Stink](http://stink.co) are the film-arm of the company I work for, and the redesign of their site has been an ongoing project for the past year or so. The previous site had a separately managed version for each office, all of which were to be combined into Stink.co - the go-to site for Stink worldwide.

### The tech side

The design and build of the site is mobile-first; starting with the early designs using a narrow-viewport, and the CSS by default shows the mobile version, with breakpoints set to relayout content as the viewport becomes wider.

The site is rendered on the server and enhanced in the browser. It works as a single-page app but doesn't make use of a JSON API like many. We opted to use a *pjax-like* method of loading the full site once, then subsequently loading the content of the next page as HTML and injecting it directly into the DOM.

On the server-side, the custom python back-end and cms cache the site so effectively that content is loaded lightening-fast making it a pleasure to view across multiple devices.
