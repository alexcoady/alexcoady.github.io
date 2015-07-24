---
layout: post
title:  Website redesign
slug: stink
project_url: http://stink.co
client: Stink films
date: 2015-03-15 00:00:00
tags: javascript film backbone
excerpt: Building the new home of Stink
role: Lead front-end developer
agency:
  name: Stinkdigital
  url: http://stinkdigital.com
---
[Stink](http://stink.co) are the film-arm of Stinkdigital; the redesign of their site had been an ongoing internal project for a year or so.

The previous site was made from 5 totally independent websites that looked similar. The new website had to merge all these sites into one larger global site that represented all the different regions.

### The tech side

The design and build of the site is mobile-first; starting with the early designs using a narrow-viewport, and the CSS by default shows the mobile version, with breakpoints set to relayout content as the viewport becomes wider.

The site is rendered on the server and enhanced in the browser. It works as a single-page app but doesn't make use of a JSON API like many. We opted to use a *pjax-like* method of loading the full site once, then subsequently loading the content of the next page as HTML and injecting it directly into the DOM. The following is the `Backbone.Model.prototype.parse()` method for the content:

{% highlight javascript %}
parse: function ( response ) {

  var tempEl = $('<temp>');
  tempEl.html( response );

  var headerEl = $(tempEl).find('#app-header');
  var navbarEl = $(tempEl).find('#app-navbar');
  var contentEl = $(tempEl).find('#app-content');

  return {
    navbarHTML: navbarEl.html(),
    filterbarHTML: filterbarEl.html(),
    contentHTML: contentEl.html()
  };
};
{% endhighlight %}

Changes to these attributes (`navbarHTML`, `filterbarHTML`, `contentHTML`, and others removed for brevity) are being watched for in their respective views and updated HTML is injected into the DOM when necessary.

On the server-side, the custom python back-end and CMS cache the site so that content is loaded lightening-fast.
