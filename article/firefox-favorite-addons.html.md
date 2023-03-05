---
title: 'My favorites plugins for Mozilla Firefox'
date: '2007-12-08T00:10:49+01:00'
status: publish
permalink: /article/firefox-favorite-addons.html
author: Snakefoot
excerpt: 'Plugins and setting tweaks for Mozilla Firefox.'
type: post
id: 761
category:
    - Firefox
tag: []
post_format: []
---
The force of Firefox has always been the vast library of available plugins and themes, which allows one to customize almost everything.  
  
 Some of these addons are promoted to be part of the core functionality of Firefox, like the Session Saver plugin, which allows one to resume the last browsing session (Sadly enough it fails its purpose if a popup window is hidding in the background. More Info [354894](https://bugzilla.mozilla.org/show_bug.cgi?id=354894)).

##### Useful settings for web surfing

- browser.startup.page = 3 (Resume previous browser session at startup)
- browser.enable\_automatic\_image\_resizing = false (Do not scale pictures)
- browser.tabs.tabMinWidth = 0 (Disable tab scroll)
- browser.tabs.selectOwnerOnClose = false (Give previous tab focus on close)
- browser.tabs.loadFolderAndReplace = false (Bookmarks should not replace existing tabs)
- network.http.max-persistent-connections-per-server = 8 (More than two downloads at once)
- network.http.max-persistent-connections-per-proxy = 12 (More than two downloads at once)

##### Addons for web surfing

- [Duplicate Tab](https://addons.mozilla.org/en-US/firefox/addon/28) - Makes a clone of the selected tab, so one can continue to read page on the selected tab while browsing the history on the newly cloned tab. More Info [Twanno](http://twanno.mozdev.org/)
- [New Tab Homepage](https://addons.mozilla.org/en-US/firefox/addon/777) - Instead of showing an empty page when opening a new tab, then it will show your homepage. More Info [Ben Basson](http://www.cusser.net/extensions/)
- [Dictionary Search](https://addons.mozilla.org/en-US/firefox/addon/68) - Allows one to submit text selected on a homepage to a search engine. This can be useful when wanting to look up the meaning of a word, or the rating of a movie. More Info [Jaap Haitsma](http://dictionarysearch.mozdev.org/)

##### Addons for web-developing

- [HTML Validator](https://addons.mozilla.org/en-US/firefox/addon/249) - Validates the web-page currently shown with very little overhead using Tidy and OpenSP. Useful if modifying the HTML of a web-page. More Info [Marc Gueury](http://users.skynet.be/mgueury/mozilla/)
- [Live HTTP Headers](https://addons.mozilla.org/en-US/firefox/addon/3829) - Useful if wanting to check if your web-server is responding with the correct 301 or 404 HTTP error code. More Info [Daniel Savard](http://livehttpheaders.mozdev.org/)
- [View Source With](https://addons.mozilla.org/en-US/firefox/addon/394) -Enables Firefox to use alternative HTML viewers / editors instead of the native viewer, when choosing view source for a web-page. More Info [Davide Ficano](http://dafizilla.sourceforge.net/)