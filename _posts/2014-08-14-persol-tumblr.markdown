---
layout: post
title:  Tumblr theme redesign
project_url: http://persol.tumblr.com/
slug: persol
client: Persol
date: 2014-08-15 00:00:00
tags: javascript film backbone
excerpt: A stripped-back Tumblr theme for Ray-Ban's premium sunglasses brand Persol
role: Lead front-end developer
agency:
  name: Stinkdigital
  url: http://stinkdigital.com
---
Ray-Ban brands use a number of different platforms to engage with their customers, often including Tumblr. Persol approached Stinkdigital wanting a new theme for their Tumblr page, which was looking outdated, and was clogged up with jQuery plugins.

Internally, the project was designed and ready for build - but nobody had written themes for Tumblr before. The designers, who were most familiar with Tumblr, spoke about the development as "just a Tumblr theme", but the reality was that the coding process was going to be seriously limited by the platform.

After a heavy learning curve, and some discovery into using either the Theme builder or a custom JS single-page app and their API, a choice to use a combination of methods was made; mostly relying on the Theme builder, with enhancements added using the API.

### The tech side

The theme is written using [Tumblr theme tags](https://www.tumblr.com/docs/en/custom_themes) which allowed me to check if the user is viewing an index page (such as the homepage, or a search page) or a permalink page (for a specific post).

All Javascript is written without a framework, but runs in a similar way to many Backbone projects. Tumblr provide a [HTTP API](https://www.tumblr.com/docs/en/api/v2#posts) which can be used to query posts and blog info; however it cannot provide everything that the Theme tags provide so I settled for a *pjax-like* method of loading new pages in HTML and swapping out content as necessary direction in the DOM.

The theme code was uploaded to Tumblr, with all assets pointing to a IP address for local Javascript and Sass development. This allowed us to share the site within our Wifi network in the office, but accessing it from anywhere else would load the content but none of the assets - obviously for development all assets were minified and hosted on Tumblr.

A lot of Tumblr theme coding falls down to hacking their theme tags. For example, you can use the following tag to check if the user is on an index page:

{% highlight html %}
{block:IndexPage}
  <!-- Index page content here -->
{/block:IndexPage}
{% endhighlight %}

... which is great; but the content shown here will be the same for the homepage, any search results and tag pages. If you want to have homepage-only style (which you almost always do) you have to write some pretty ugly code:

{% highlight html %}
{block:IndexPage}
  {block:SearchPage}<!--{block:SearchPage}
  <div class="HomepageOnly"></div>
  {block:SearchPage}-->{block:SearchPage}
{/block:IndexPage}
{% endhighlight %}

This comments out the homepage only code on search result pages. It's not pretty, but it's the best solution at the moment.
