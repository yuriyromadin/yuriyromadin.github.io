---
layout: post
title: How to enable picture-in-picture mode for Youtube on iPad
date:   2018-08-11 21:54:00 +0300
permalink: pip-for-youtube-on-ipad
comments: true
background: /assets/img/pip-for-youtube-on-ipad.jpg
---
Since iOS 11, Apple introduced new feature for iPads, that let you use your
apps while watching video in the small floating window.

Unfortunately, Youtube did not add this functionality to their application for
iPad. They force you to always use Youtube in the foreground. The only workaround
is to launch two applications side by side using multitasking mode:

![Youtube multi tasking mode on iPad]({{ "/assets/img/split-screen-mode.png" | absolute_url }})


## The problem
While split screen mode is useful and kinda solves our problem, and you can use
all built-in apps in this mode, not all 3rd party apps support this mode.

Also, as you can see from example above, a lot of screen estate is not used,
especially when iPad's in portrait mode.

## Solution?
Unfortunately, solution is not elegant enough, but it works!
To use this "hack", you will have to use Safari, instead of Youtube
native application. I know, I know, the mobile UI of Youtube website is not
good, but hey, it's still usable.

### Step 1:
You will need to create new bookmarklet - it's a bookmark stored in a web browser
that contains JavaScript commands that add new features to the browser.

The Javascript code behind all this is super simple and only contains one line:

{% highlight javascript %}

document.querySelector('video').webkitEnterFullScreen();

{% endhighlight %}

If you are not familiar with bookmarklets, just open Safari on your iPad or Mac computer and drag&drop this link to your favourites bar:

[Youtube FullScreen](javascript:(function(){document.querySelector('video').webkitEnterFullScreen()})();)

### Step 2:
That's it! 😎 Just browse any Youtube video from your Safari browser, and when you are
on the video page just click on "Youtube FullScreen" bookmark you just created.
It will automatically open video in fullscreen mode, and from there you can
press on picture-in-picture icon to minimize your video into floating video player.

After that you can open any other application and your video will be floating on top of it:

![Youtube picture in picture mode for iPad]({{ "/assets/img/picture-in-picture-on-ipad.png" | absolute_url }})

Btw, did I tell you it works flawlessly both on iPad and your Mac computer?

![Youtube picture in picture mode for Mac OS X]({{ "/assets/img/youtube-picture-in-picture-on-macosx.png" | absolute_url }})


## Conclusion
Obviously this method won't fit all use cases, but at least it gives you an option.

There are a few pros and cons I want to mention:

### Pros
- You can launch any Youtube video in picture-in-picture mode and continue to use other applications while video is playing, even in the background.
- Safari supports content blockers, so you can avoid ads during the video (don't forget to support your favourite content creators in other ways, for example with donation).
- You can change video player size, and even swipe it off from the screen, and video will still play in the background.
- You get iOS/Mac OS X native video player with all the controls in all the right places.

### Cons
- You have to use Youtube mobile website version, which really is pain in the ass.
- The maximum video quality is 720p.
- If you keep native Youtube application, all Youtube links you click, will be opened in Youtube application, so you will have to make additional actions to open videos in Safari.
- You loose Youtube's auto-quality selection feature based on your current internet speed. So if you're traveling and entering slow internet area, your video will stutter.
- Other applications that run in the foreground may "steal your sound" and then your video will be paused (this happens everytime there's ad with sound in the application)
