<!-- TITLE: Double Click -->
<!-- SUBTITLE: A quick summary of Double Click -->

# Doubleclick Guidelines

This page takes you through how to upload ads to the Doubleclick platform. Below are also a list of code snippets and bits to help you build and ad.

## Platform URL
Plaform url: [https://www.google.com/doubleclick/studio/](https://www.google.com/doubleclick/studio/)

You should be able to log in with your Think Jam email. If you don't have access please speak to the Lead Developer who can sort you an access.

## uploading an ad

Each ad is uploaded to a specific campaign, the campaign you need to upload it to should be on the brief in trello. If the campaign isnt on the brief check with the relevant producer.

Either click on the campaign on click new creative in DC which will take you to the upload page:

![Dc Upload](/uploads/dc-upload.jpg "Dc Upload")

fill in all the relevent details. Format type is usually in-page unless its specific to the template, if you're not sure check with the lead developer or the producer on the brief. Filename is always the same as the PSD and should be found on the brief - but again if not sure check with the producer.

next you'll go to to the manage files section. Zip up all your files in your HTML folder and drop them onto the page. they'll then be uploaded and processed. once they're on the platform - select the backup image by ticking the 'use as backup image' next to the right image

## Adding Exits
For each exit you added to the code (See Clicktag) you should add a URL in the DC platform. URL's will be provided on the brief.

go to the edit events tab and ad each URL into the destination box

![Events](/uploads/events.jpg "Events")

## QA and delivery

When you've uploaded the ad and added all the exits. go to the preview tab. here you should check that the ad loads and clicks through to the right URL's.

For each ad you should also check:

* All videos are tracking properly. See Metrics below
* Any Custom tracking is firing properly.
* ***that there are no javascript errors in the console* 

To check metrics (video tracking, custom tracking etc) you should click the 'i' button and look at the **Event Summary/Output Console** box. if the tracking is firing correctly you'll see the count change at the appropriate point. Eg. when the video is halfway through the console should update the Video midpoint tracking.

![Events Console](/uploads/events-console.jpg "Events Console")


To check on a device, in the preview tab, click preview location and then Scan QR code - you'll then get a QR code you can scan to open up on your phone.

When you're satisfied everything is fine, copy the preview URL in chromes browser window and send it back to the producer on the brief.

## Making Changes

If you have to make any changes, such as amends from the producer - you should repeat the steps above each time. The only main difference is you don't have to rezip all the assets each time to upload the files in the manage files section, you can just upload the changed files instead.


## Building and ad and Doubleclick code snippets

Reference page for coding examples [here](https://www.google.com/doubleclick/studio/docs/sdk/html5/en/class_studio_Enabler.html).

### Include the enabler

Every DC ad needs to have the enabler script included. This is added in the `<head>` section of the primary HTML document


```html
<script src="https://s0.2mdn.net/ads/studio/Enabler.js">
</script>
```


### Initialise DC inside the javascript

Once the enabler is loaded in the HTML, the next step is to initialise DC from within the javascript. This ensures that the platform API is fully connected before starting the ad, which ensures clicks, trackings and impressions all work effectively. This is done by adding an init function on page load:

```javascript
//onload function added to bottom of JS
window.addEventListener('load', init);

//init function added at top of JS/after variables defined

function init() {

    // Polite loading - launch enabler. Once loaded calls the startAd function
    if (Enabler.isInitialized()) {
        startAd();
    } else {
        Enabler.addEventListener(studio.events.StudioEvent.VISIBLE, startAd);
    }
		
		// Enabler is now loaded so lets start the ad
    function startAd(){

      // run code to start ad.

    }

}
```

### Clicktag

This is the exit code used to apply a clickthough to a DC ad. This would go in place of a javascript URL, usually found in the exithandler function.

The variable can be repeated as many times as you need for the add, but try to keep it descriptive to the ad.

The URL is applied to the ad inside the platform on the 'Edit Events' page.

```javascript
Enabler.exit("Main");
```


### Video Tracking

Each video should have tracking applied to it. you can use Doubleclick's auto tracking module for single videos, below. For multiple videos we use custom tracking code which you can find in our media templates on Box

```javascript
// define variable for video element
var video1 = document.getElementById('video1');

// in the addeventlistener function, add in this script to apply tracking. last argument should be the same as the variable defined.
Enabler.loadModule(studio.module.ModuleId.VIDEO, function() {
    studio.video.Reporter.attach('video_1', video1);
});
```


