---
layout: post
title: Messing with Jekyll pt. 2
---

My gosh this was a more nebulous process than I could ever have imagined... the transition to Github 3.0 has left a heaping mess. There is little documentation on the github pages, it essentially assumes that you'll use base template and make minimal changes... which is great, but the jump to get a custom page working is a little bit more esoteric. Most examples have something that complains in the Jekyll building process, suggestions that are esoteric.


## Gotchas 

1. The relative pathing for a doesn't work you need to have the full url. The relative paths break on sub-pages of the static site.
2. The structure of the application will break the page if you do not have the correct folders and the content, this is really opaque, and can only be debugged locally, which defeats the simplified format of the page...

## Sources I've used

1. [Jekyll-Now self promotion...](https://www.smashingmagazine.com/2014/08/build-blog-jekyll-github-pages/)
2. [Github blog, especially the post about Jekyll 3.0 and how it's been simplified](https://github.blog/2016-02-01-github-pages-now-faster-and-simpler-with-jekyll-3-0/) 
3. [Lanyon slide bar theme as a base which I'll modify later](http://lanyon.getpoole.com/)

