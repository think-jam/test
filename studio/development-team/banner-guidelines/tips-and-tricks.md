<!-- TITLE: Tips And Tricks -->
<!-- SUBTITLE: A quick summary of Tips And Tricks -->

# Banners - Tips and Tricks
This page contains links to our tips, tricks and general help collated for helping with banner development


## Tips
* We normally use imgs and no text/fonts 
* Media is usually built using just img and div tags
* Most ads are datecoded using a datecoding script - https://thinkjam.app.box.com/file/224911136577
* Every ad should have a click tag around the whole ad, this is normally done in the JS as it sometimes needs to be customised for different ad platforms
* Click tags should always open the url in a new tab
* All ads have a 1px border
* Ads normally have a max file weight so assets have to be saved down using things like tinypng. This is normally set out in the brief.


## Definitions
* **Static Media** - non-HTML ads, just images.
* **Standard Media** - Ads with no video content, just images and animation.
* **Rich Media** - Ads with video content
* **MPU** - A 300px X 250px ad
* **Leaderboard** - A 728px X 90px ad
* **Skyscraper** - A 160px X 600px ad 
* **Expandable** - An ad that expands to another size onclick e.g. 300x250 - 500x250
* **Progressive** - A ad with a progressive video that autoplays without controls or audio
* **In Page** - A ad with a video that plays with controls and audio and only autoplays muted with a click for audio button
* **Interstitial** - This is normally a popup that shows before a website has loaded and floats in the center of the page. Different ad platforms have differing templates for their * Interstitials. e.g. [http://think-jam.celtra.com/preview/363bb0c7#deviceType=Phone](http://think-jam.celtra.com/preview/363bb0c7#deviceType=Phone)
* **Takeover** - This can come in multiple different styles but basically means an ad that takes over an website, normally using a skin and a leader board and sometimes also a expandable section. e.g. [http://showcase.thinkjam.com/projects/trolls/weischer/](http://showcase.thinkjam.com/projects/trolls/weischer/)
* **Overlay** - An ad that complete overlays a site e.g. [http://collectivedemos.com/hit-preview/90-min/preview.php?adid=37968446](http://collectivedemos.com/hit-preview/90-min/preview.php?adid=37968446)
* **Site-Served** - When ads are built and sent directly to the site to be hosted rather than using a ad platform. 
* **Ad Platform** - A website that host ads, they normally have their own click tags and sometimes ways of tracking videos. Once a ad is built is uploaded to the platform to then be trafficked out to a website. 
* **CTA** - Call to action, a element like a button that calls the user to click out e.g. Watch Trailer or Book Tickets. 
* **Click Tag** - A snippet of javascript that triggers and exit to another url on click of the ad, sometimes ads will have multiple clicktags a main one and one on the CTA. 
*  **Impression** - a metric logged by an ad platform to show how many times the ad was loaded
*  **Backup image** - a low res image used by ad platforms if javascript is disabled in the browser. Usually counts towards total fileweight


 