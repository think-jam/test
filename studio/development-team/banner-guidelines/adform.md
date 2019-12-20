<!-- TITLE: Adform -->
<!-- SUBTITLE: Adform coding guidelines -->


# Adform Guidelines

This page takes you through how to upload ads to the Adform platform. Below are also a list of code snippets and bits to help you build and ad.



## Platform URL
Plaform url: [https://studio.adform.com](https://studio.adform.com/)

Click login -> login via github. We use **developers@thinkjam.com** as the account and you should be able to access this via one login. If not speak to the lead developer.

## uploading an ad

On the ad dashboard page, zip up your files and drag and drop them to the window. Alternatively you can click New -> Upload Banner.

![Adform Upload](/uploads/adform-upload.jpg "Adform Upload")

fill in all the relevent details. Category is usually display and the format is usually standard unless its specific to the template, if you're not sure or its not on the brief check with the lead developer or the producer on the brief. 

You'll then go through to the banner window make sure the title has the right filename. Filename is always the same as the PSD and should be found on the brief - but again if not sure check with the producer.

## Adding Exits
For each exit you added to the code (See Clicktag) you should add a URL in the Adform platform. URL's will be provided on the brief.

Scrolldown to the clicktags section. Adform only usually ads in the first clicktag, and for each additional one you have to add them yourself. Click Add Clicktag, variable names are usually clicktag1, clicktag2 and so on with Adform.

![Adformclicktag](/uploads/adformclicktag.png "Adformclicktag")

## QA and delivery

When you've uploaded the ad and added all the exits. Click the ad preview button here you should check that the ad loads and clicks through to the right URL's. You'll know the click through is tracking properly as before the page loads there will be a visual confirmation in the platform

For each ad you should also check:

* **That there are no javascript errors in the console**


To check on a device, in the preview tab, click preview location and then Scan QR code - you'll then get a QR code you can scan to open up on your phone.

When you're satisfied everything is fine, copy the preview URL in chromes browser window and send it back to the producer on the brief.

## Making Changes

If you have to make any changes, such as amends from the producer - make the changes locally on your machine and then click on the file browser butotn on adform

![Filebrowser](/uploads/filebrowser.png "Filebrowser")

For each file you've changed, click the three dots then click Reupload file to replace it.

## Building and ad and Adform code snippets

Reference page for coding examples [here](https://support.adform.com/documentation/).

### Include the API

Every Adform ad needs to have the API script included. This is added in the `<head>` section of the primary HTML document


```html
<script>
document.write('<script src="'+ (window.API_URL || 'https://s1.adform.net/banners/scripts/rmb/Adform.DHTML.js?bv='+ Math.random()) +'"><\/script>');
</script>
```



### Clicktag

This is the exit code used to apply a clickthough to an Adform ad. This would go in place of a javascript URL, usually found in the exithandler function.

The variable can be repeated as many times as you need for the add, but for the variables, you should use clickTag1, clickTag2 and so on for each additional URL.

The URL is applied to the ad inside the platform in the 'Click Tags' section.

```javascript
var clickArea = document.getElementById('clickLayer');
clickTAGvalue = dhtml.getVar('clickTAG', 'http://www.example.com');
landingpagetarget = dhtml.getVar('landingPageTarget', '_blank');
clickArea.onclick = function() {
    window.open(clickTAGvalue,landingpagetarget);
}
```





