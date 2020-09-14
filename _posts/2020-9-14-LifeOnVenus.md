---
layout: post
title: Did we find life on Venus?
---

No.\*

But a group of researchers based in the UK, US and Japan did just publish [observations](https://www.nature.com/articles/s41550-020-1174-4) of a gas on Venus that is produced by living organisms under certain conditions here on Earth and, according to their models, is unlikely to have been formed by currently-know abiotic (non-living) chemistry! It's nowhere near proof that life exists on the planet, but still very exciting and will hopefully lead to funding for missions to get more direct observations.

The reason for this post is not the announcement itself, but the reaction to the results getting leaked ahead of time and how it could be tracked in real time!

Earlier in the day, I saw a few tweets making oblique references to Venus, life and phosphine. I vaguely recognised the last one as some chemical compound, but the tweets were very vague and confusing. So I turned to trusty Google and found some oddly broken links to news stories from one day ago about the discovery, followed by a working Medium post that explained everything!

Apparently, the story was sent to press outlets under what is called an "embargo", which is something pretty common that gives journalists time to prepare their pieces to be released at the same time the paper gets published in an academic journal. **But**, one (or more) of those outlets released their piece ahead of time and the rumour started spreading, eventually reaching my eyes.

I thought that was pretty interesting and wondered how many other people like me were probably a lot more interested in Venus and phosphine than expected on any given Monday morning! Luckily, Google exposes a tiny sliver of their mountains of data on our searches through the [Trends](https://trends.google.com) site and it was pretty obvious that interest in those terms was trending way above their baselines, especially for phosphine:

<script type="text/javascript" src="https://ssl.gstatic.com/trends_nrtr/2213_RC01/embed_loader.js"></script> <script type="text/javascript"> trends.embed.renderExploreWidget("TIMESERIES", {"comparisonItem":[{"keyword":"/m/01n6rt","geo":"","time":"now 7-d"},{"keyword":"/m/01_1nb","geo":"","time":"now 7-d"},{"keyword":"/m/09bcm","geo":"","time":"now 7-d"}],"category":0,"property":""}, {"exploreQuery":"date=now%207-d&q=%2Fm%2F01n6rt,%2Fm%2F01_1nb,%2Fm%2F09bcm","guestPath":"https://trends.google.com:443/trends/embed/"}); </script>
*Plot of interest over time in the search terms "Venus", "phosphine", and "Royal Astronomical Society"\*\*, for the last 7 days. \*\*\*

I also tried expanding the date range to see if maybe the baseline at 7 days was already elevated from a leak within smaller groups:

<script type="text/javascript" src="https://ssl.gstatic.com/trends_nrtr/2213_RC01/embed_loader.js"></script> <script type="text/javascript"> trends.embed.renderExploreWidget("TIMESERIES", {"comparisonItem":[{"keyword":"/m/01n6rt","geo":"","time":"today 1-m"},{"keyword":"/m/01_1nb","geo":"","time":"today 1-m"},{"keyword":"/m/09bcm","geo":"","time":"today 1-m"}],"category":0,"property":""}, {"exploreQuery":"date=today%201-m&q=%2Fm%2F01n6rt,%2Fm%2F01_1nb,%2Fm%2F09bcm","guestPath":"https://trends.google.com:443/trends/embed/"}); </script> 
*Plot of interest over time in the search terms "Venus", "phosphine", and "Royal Astronomical Society"\*\*, for the last 30 days. \*\*\*

This one is fairly flat for all terms and even the uptick that happened today is not visible. This is probably because the data for the monthly plot is not updated as often as the weekly one, so this might show a spike by tomorrow.

I thought this was worth a post mainly to highlight how cool it is that we can get near-realtime access to data on how a story is getting quickly spread globally, all from a single news source leaking it!

I also just found that there is a [python API](https://pypi.org/project/pytrends/) for Google Trends, so I'll tinker with it a bit and possibly revisit Trends for some future post.


## Footnotes

\*See [Betteridge's law of headlines](https://en.wikipedia.org/wiki/Betteridge's_law_of_headlines)

\*\* I added this term because I saw that the RAS would do a live announcement a few hours later, and there was indeed an uptick in searches for them, followed by a decline down to baseline now that the announcement is past.

\*\*\* These plots will auto-update constantly and interest will probably wane soon, so I'll put screenshots of their current versions as of the time of this post below, so that my text still makes some sense after today.

![Trends 7days]({{ site.baseurl }}/images/venus-phosphine-7days.png)
![Trends 30days]({{ site.baseurl }}/images/venus-phosphine-30days.png)
