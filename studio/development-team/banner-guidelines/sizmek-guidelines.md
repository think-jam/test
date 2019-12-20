<!-- TITLE: Sizmek -->
<!-- SUBTITLE: Sizmek coding guidelines -->

# Sizmek Guidelines

This page takes you through how to upload ads to the Sizmek platform. Below are also a list of code snippets and bits to help you build and ad.

## Platform URL
Plaform url: [https://www.sizmek.com/](https://www.sizmek.com/)

There are 2 platforms for Sizmek, MDX and SAS - MDX is the older platform so we dont often publish ads there, so this article concentrates on SAS (Sizmek Ad Suite)

## uploading an ad

to upload assets, click Creatives -> Asset Library.

When in the Asset Library, go into the relevent campain folder. All ads for a particular film should be in one folder. If no film folder exits, create one by clicking new folder.

Once in the right folder. click **Add New Asset**

Zip up your whole ad and drag and drop in to the upload wizard

On the ad dashboard page, zip up your files and drag and drop them to the window. Alternatively you can click New -> Upload Banner.

![Upload Window](/uploads/screenshot-2019-03-20-at-11-03-17.png "Upload Window")

## Creating an Ad

Once your assets are uploaded, you can create the ad.

Click Creatives -> Ads then click the more button on the right hand side and click the new ad -> blank ad button

![Sizmek New Ad](/uploads/sizmek-new-ad.png "Sizmek New Ad")

Fill in the relevent details. 

Adformat: unless specified in the brief, it's usually HTML5 Rich Media Banner

The next thing you need to do is assign two things, the workspace and the backup.

The workspace is the zip file you added earlier, so click assign asset and navigate to the zip file and select.

Then you need to assign the backup image (Default Image) - which should be in the zip file. click assign asset and again navigate to the right file.

![Sizmek Ad Creation 1](/uploads/sizmek-ad-creation-1.png "Sizmek Ad Creation 1")


## Adding Exits

Scroll down and add the exit to the clickthrouh section on the ad page.

If you have coded in any extra clickthroughs, they should show up in the events section, and you can paste in your URLs there.

## QA and delivery

When you've uploaded the ad and added all the exits. Click the ad preview button here you should check that the ad loads and clicks through to the right URL's. 

For each ad you should also check:

* **That there are no javascript errors in the console**


When you're satisfied everything is fine, copy the preview URL in chromes browser window and send it back to the producer on the brief.

## Making Changes

If you have to make any changes, such as amends from the producer - make the changes locally on your machine and then replace the assets in the asset library on sizmek.

For each file you've changed, you have to navigate to that file, and select it and click replace

## Building and ad and Adform code snippets

Reference page for coding examples [here](https://developers.sizmek.com/hc/en-us/sections/201689733-Getting-Started).

### Include the API

Every Sizmek ad needs to have the API script included. This is added in the `<head>` section of the primary HTML document


```html
<script type="text/javascript" src="https://secure-ds.serving-sys.com/BurstingScript/EBLoader.js"></script>

```

once it's included, you need to initialize the script in the startAd function:

```javascript
//on load:
window.addEventListener('load', startAd);

// start ad
function startAd() {

    if (!EB.isInitialized()) {
        EB.addEventListener(EBG.EventName.EB_INITIALIZED, onInit);
        // This code checks whether the EB object is initialized, if the object is initialized, it launches the function "onInit", otherwise "EB_INITIALIZED" event.
    } else {
        onInit();
    }

    function onInit() {
        // Place your code to start the ad flow here
       
    }

}
```



### Clicktag

This is the exit code used to apply a clickthough to an Sizmek ad. This would go in place of a javascript URL, usually found in the exithandler function.

EB.clickthrough is used for the main CTA. If you need a secondary clickthrough, or multiples, use EB.userActionCounter.

example:


```javascript
function onExitHandler(exit) {

    switch (exit) {
        case "main":
            EB.clickthrough();
            break;
        case "cta":
            EB.userActionCounter("CTA");
            break;
    }
}
```





