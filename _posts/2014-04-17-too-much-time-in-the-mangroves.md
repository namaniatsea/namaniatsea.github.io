---
title: Too much time in the mangroves...
type: namani_blog_post
author: Sailing up the Queensland coast
layout: post
frontpage: true
location: Rosslyn Bay
position_lat: -23.161666666700
position_lon: 150.788333333300
---
While we were holed up in Pacific Creek, waiting for TC Ita to pass, I was playing around with the metadata (i.e. the timestamps, camera settings, etc. that are stored in image file) of the thousands of pictures we've taken along the way.  Maybe there's a way to make these numbers tell some kind of a story - the 30,000ft view of our trip?  The strange things you do when you're boat bound in a mangrove swamp for a week...

After extracting the full metadata from from the last 2.5 years' ~14,000 image files on our harddisk, the first challenge was to trim this set down to include only 'unique' photos. By 'unique' I mean excluding all those "I'll take another one just to be safe" pictures, that leave you with 20 nearly identical photos of yet another tropical sunset. Nana is much better at culling these, but for me they just accumulate. It turned out that an easy way to do this was simply to exclude all images that were taken within less than 10 seconds of the respective previous image. Not a perfect filter but eyeballing a few examples showed that it does quite a good job of getting rid of the redundancy. And since I'm only interested in approximate times, locations, etc. I'm not worried about picking the best shot in each case.

This left us with data from a little less than 10,000 photos, each of which represents some unique moment along our way.

A first shot was simply to plot how these 10,000 accumulated over time:

<img src="http://dropbox.namaniatsea.org/blog_images/exif_plots/cumulative_count_800.png" alt="" />

Hmmm... not hugely insightful. You can see that our picture taking slowed down somewhat during our second season in the tropics, and there are a few bumps and dips, but otherwise this looks pretty boring.

How about taking a daily pulse of our "shutter happiness"? That looks like this:

<img src="http://dropbox.namaniatsea.org/blog_images/exif_plots/daily_counts_bar_800.png" alt="" />

Wow - that's a bit too much information.  You can see some obvious spikes (e.g. our Panama Canal transit in January 15, 2012) but there is a bit too much noise to do anything useful with it.

OK, let's try a mix between the two: How about a rolling 7-day average of our daily shutter count. So three successive moderately active days may get the same weight as one spectacular day during a week where not much else happened (seems reasonable - eh?).

Here's the plot:

<img src="http://dropbox.namaniatsea.org/blog_images/exif_plots/rolling_mean_raw_800.png" alt="" />

Now that starts to look interesting... following the ups and downs we can actually tell pretty easily what each of these relates to.  Here's an annotated version:


<img src="http://dropbox.namaniatsea.org/blog_images/exif_plots/rolling_mean_annotated_800.png" alt="" />

OK, let's try a different perspective. The NSA has been complaining that they couldn't track our cell phone over the past few years. So we'll help them out and look at how our shutter count spreads across locations. A slight problem: We keep the GPS receiver in our cameras switched off because it draina the battery much too quickly. Hence we don't have location data stored in our image files.  But we do have a reasonable record of Namani's position over time, and we can simply interpolate based on each photo's timestamp.

So we do that and plot a heatmap of our shutter count by latitude and longitude:


<img src="http://dropbox.namaniatsea.org/blog_images/exif_plots/hexbin.png" alt="" />

That looks a bit like the things you see after a few bowls of kava on an island in Vanuatu... maybe some context helps:

<img src="http://dropbox.namaniatsea.org/blog_images/exif_plots/hexbin_with_map.png" alt="" />

The thin line is Namani's approximate track from Maine to Australia. 

Panama comes out red-hot- a combination of spending a whole three months there plus some hard-hitting days like the canal transits on Namani, Astarte and Wilhelm (the two boats we line handled for).  The Galapagos come out 'warm' (only three weeks, and heavily impacted by the "no less than 10 seconds" rule).  Around 120 degrees West you can actually see a little warm spot in mid-Pacific, about 2/3 of the way between the Galapagos and the Marquesas.  That was our mid-Ocean rendezvous and photo shoot with ECapoe.

Fatu Hiva and Bora Bora/Maupiti stick out in French Polynesia and Suwarrow (at about 170W) clearly made it onto the map as well.

New Zealand shows another red-hot spot -  no wonder: you can take a lot of pictures in six months... and that doesn't even count Tauranga and the South Island which were broken out into separate cells.

In any case... we're out of the swamp again, so we can turn our attention to more meaningful things instead ;-)

***

PS: a small "lesson learned" from the exercise above... The EXIF DateTimeOriginal tag that stores when a picture was originally taken (rather than the image file being copied or modified) does not store timezone information. We have more or less kept the clock in our cameras set to local time where ever we were. In hindsight it would have been better to leave the clocks set to UTC (or some other fixed reference time). This would make the aggregate analysis above a bit easier and more exact.
