# [AMP Project](https://www.ampproject.org/)

This was the first ever AMP roadshow in India, and it turned out to be a nice intro for me into AMP. 
I've been seeing it everywhere on my google search results, was happy that it loaded almost instantaneously, 
and all my curiousity about how it works, how it achieves all of this was quelled.

So, let's look at the basics: **What AMP promises**
* Blazing fast load
* Easy to create AMP pages
* FOSS

How does it fare on all those counts?
* They showcased AliExpress's e-commerce website, complete with search, 
filter on the product listing page to the product description etc **load at around 0.5s**
* They ship a [whole bunch of components](https://www.ampproject.org/docs/reference/components) that you can build the UI with from carousels, 
media players to widgets for embedding youtube, twitter, instagram content. And what's more all of these components are optimized to load faster
* Their entire project is [open sourced](https://github.com/ampproject/amphtml) and there was a 
mention of creating a foundation to manage and oversee the development of AMP project

## What's the magic behind this?

From what I could understand this is how it achieves all that it promises!
* Each AMP Page is written in an opinionated way using their AMP components which allows very minimal configuration 
but still is good enough for most of the usage.
* They force you to give fixed width & height for your images, iframes, your embedded content etc. 
So that it has to calculate the layout once when it loads. No more content jumping up and down, after your images start loading.
* All the CSS for that page has to be inlined, and it cannot be more than 50kb. What this helps is, without having to make a roundtrip for fetching CSS
your page suddenly change it's look immediately after it's loaded.
* All your AMP Pages are cached using the AMP cache, which serves the pages for you as fast as possible.
* Another restriction that needs to be pointed out is that it doesn't allow any custom JS on the page.

All the points I have mentioned above sounds very much benefitting the static data. Right? AMP allows you to be dynamic as well.

* AMP provides you a [`amp-list`](https://www.ampproject.org/docs/reference/components/amp-list) component, which allows you to make
a request to your backend and render the resulting data using Mustache templates.

## How can we use this?

Since we have a huge e-commerce website, not everything needs to be converted to AMP, the best strategy is to make all your entrypoints into your website in AMP, so that it loads faster which also helps in SEO. Once the user opens up intial page which is in AMP, we could upgrade that user to a full PWA experience using service worker ([`amp-install-serviceworker`](https://www.ampproject.org/docs/reference/components/amp-install-serviceworker)). So the rest of the user experience will be in the full fledged webapp.

And the component library even consists of things like [`amp-analytics`](https://www.ampproject.org/docs/reference/components/amp-analytics) which allows you to add analytics from a variety of vendors. And there are a lot of AD networks who have converted their ads into AMP as well so that is also a plus. You can even do things like A/B testing using [`amp-experiment`](https://www.ampproject.org/docs/reference/components/amp-experiment) and serve geo based content using [`amp-geo`](https://www.ampproject.org/docs/reference/components/amp-geo) and even personalize content via [`amp-access`](https://www.ampproject.org/docs/reference/components/amp-access).

The [AMP docs](https://www.ampproject.org/docs/) are very well written with component references, intro guides, tutorials with videos etc.
