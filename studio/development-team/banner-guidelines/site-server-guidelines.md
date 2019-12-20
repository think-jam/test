<!-- TITLE: Site Served Guidelines -->
<!-- SUBTITLE: A quick summary of Site Served Guidelines -->

# Site Served Ad Guidelines

Site server ads are essentially 'Platform free' ads. This means there are no platform scripts, or special clickthroughs, tracking etc you need to worry about.

you should follow site served template guidelines here: [https://thinkjam.box.com/s/txonypoxh4u4i6pt93a0ejkup5hsbkrs](https://thinkjam.box.com/s/txonypoxh4u4i6pt93a0ejkup5hsbkrs)

## Delivering an ad to a producer
After you've built your ad, you should run all images through [https://tinypng.com/](tinypng) then zip all the files up.

The Zip filename should **never** be archive, it should match the filename in the brief, usually the same as the PSD in the folder.

once zipped. move the ad into a **Delivery** folder in the ad structure, then copy that link and send to the producer on the brief.

## Making Changes
If you need to make any changes, you should go through the delivering steps above again each time you make changes.

## Code Snippets for Site Served ads

## Exit Handler function

```javascript
function onExitHandler(exit){

    switch (exit) {
        case "main":
            window.open("https://www.google.com", "_blank");
            break;
        case "cta":
            window.open("https://www.google.com", "_blank");
            break;
    }
}
```