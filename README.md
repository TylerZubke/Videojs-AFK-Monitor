# Videojs-AFK-Monitor
A plugin for VideoJS that is similar to Netflix's "Are you still watching?" 
Watches the 'useractive' and 'userinactive' events from VideoJS. After a certain period of inactivity a popup will display asking the user if they are still watching. If the user doesn't answer after a specified period of time, the player is automatically paused.

## How to use
Load VideoJS (http://videojs.com/) somewhere before the plugin JS file.
It can be loaded via CDN with 
```
<script src="http://vjs.zencdn.net/5.4.4/video.js"></script>
```
Load the CSS in the head tag
```
<link href="videojs.afk-monitor.min.css" rel="stylesheet">
```

Load the JS just before the close of the body tag
```
<script src="videojs.afk-monitor.min.js"></script>
```
Add the plugin to your VideoJS player (replace 'my-video' with whatever your player's ID is) 
and pass in an object of any options you wish to override.
```
<script type="text/javascript">
    var video = videojs('my-video');
    video.AFKMonitor();
</script>
```

## Options
* `containerText [String]` Text to display on the popup. The default is "Are you still watching?"
* `containerClass [String]` Extra class(es) you want to add to the container for your own styling. Separate multiple classes with a space.
* `continueButtonText [String]` Text to display on button to continue watching. Default is "Yes, Continue"
* `continueButtonClass [String]` Extra class(es) you want to add to the continue button for your own styling. Separate multiple classes with a space.
* `stopButtonText [String]` Text to display on button to stop watching. Default is "Yes, Continue"
* `stopButtonClass [String]` Extra class(es) you want to add to the stop button for your own styling. Separate multiple classes with a space.
* `waitClass [String]` Before showing the popup, the plugin will check to see if the player has the class specified with this option. If it does, the plugin will check every 10 seconds and show the popup once the class is gone. Useful if you don't want to show the popup during an ad. 
* `showMessageAfter [Number]` Amount of time (in milliseconds) the user needs to be inactive before showing the popup. Default is 20 minutes
* `pausePlayerAfter [Number]` Amount of time (in milliseconds) after showing the popup to pause the player.
* `continueButtonClickHandler [Function]` If you want to do something other than continue playing the video when the user clicks to continue watching. Context is the player object.
* `stopButtonClickHandler [Function]` If you want to do something other than reset the player back to the initial state when the user clicks to stop watching. Context is the player object.
* `ignoreUserActive [Boolean]` Message will show after specified amount of time regardless of whether userActive event is fired in that time.
