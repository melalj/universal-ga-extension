Universal Analytics for Google Chrome Extensions
======================

Javascript script that allows adding Universal Google analytics snippet to a chrome extension.

Configuration
------------
    
You just need to add this snippet code to the bottom of your pages (or create it in a separate .js) : 

    ga = new ExtGA({
        trackingId : "UA-XXXX-XX", // Your Tracking Id
        trackingDns : "my-extension.com", // Domain name that you created for the profile
        appVersion : "1.0", // application Version
        appName : "My App", // application Name
        getPref : MyTools.getPref, // (optional) If you want to use a custom function for localSettings
        setPref : MyTools.setPref// (optional) If you want to use a custom function for localSettings
    });
    
You can also add the user Id just after defing "ga" object or later.
    
    ga.setUid(10101); // User Id of my Application for crossdevice tracking
    
Usage
------------

Page view

    ga.pageview("Page Title", "/path-page");

Event

    ga.event("Event Category", "Event Action"); // Event category & action are required
    ga.event("Event Category", "Event Action", "Event Label"  12); // 12 is the event Value

Social interactions - [Check here for more info](https://developers.google.com/analytics/devguides/collection/gajs/gaTrackingSocial)

    ga.social("like", "facebook",  "/target-page"); // Facebook Like
    ga.social("share", "facebook",  "/target-page"); // Facebook Share
    ga.social("tweet", "twitter",  "/target-page"); // Twitter

Exception

    ga.exception("Error Description", 1); // 1 if it fatal, 0 if not

External Links
------------
* [Google developer Measurement Protocol Parameter Reference](https://developers.google.com/analytics/devguides/collection/protocol/v1/parameters)

    
