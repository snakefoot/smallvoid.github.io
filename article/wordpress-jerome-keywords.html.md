---
title: 'Jerome''s keywords for Wordpress 2.0'
date: '2007-09-22T14:44:50+02:00'
status: publish
permalink: /article/wordpress-jerome-keywords.html
author: Snakefoot
excerpt: 'Description of the different updates and fixes available for Jerome''s keywords.'
type: post
id: 746
category:
    - Uncategorized
tag:
    - jerome-keywords
    - tagging
    - wordpress
    - wp-plugin
post_format: []
tags:
    - 'wordpress,jerome-keywords,tagging,plugins'
---
Wordpress 2.0 doesn't have taxonomy support for tagging, but it is possible to install plugins which can extend Wordpress with support for tags:

- [Ultimate Tag Warrior (UTW)](http://www.neato.co.nz/ultimate-tag-warrior/) by Christine Davis is a very popular plugin, which creates separate tables to keep tags for the sake of performance. Out of the box it can generate a tag cloud and display posts with tag.
- [Simple Tagging](http://sw-guide.de/wordpress/plugins/simple-tagging/) says it is faster than UTW. Out of the box it provides features liked tag-cloud, display posts with tag, related tags and related posts using tags (Requires WP 2.1+).
- [Jerome's Keywords](http://vapourtrails.ca/wp-keywords) stores the tags as meta data for each post in the standard wordpress database table. As the meta table isn't optimized for tagging, then it will not show optimal performance. Out of the box it can generate a tag cloud and display posts with tag (There is BETA version of Jerome's Keywords which uses a separate database table but requires WP 2.1+).
 
 I chose to use Jerome's Keywords ver. 1.9 as I like the way it uses the existing wordpress database tables (So not using the BETA version). Jerome's Keywords is no longer being updated by the author, so bugs discovered are not fixed and no new features are added either. But there are people who still uses the plugin and creates new patches for it:
- [Fix for tag lookup with Jerome’s Keywords plugin](http://www.chipstips.com/?p=146) - Instead of finding all posts which has a tag that matches the beginning of the tag being looked up, then it only finds posts with exact tag match.
- [Jerome's Keyword Manager](http://johannes.jarolim.com/blog/wordpress/jeromes-keyword-manager/) - Plugin which makes it easier to manage tags by providing the ability to rename, delete and browse posts in tag-cloud. Applied a little fix to the plugin so when updating tags, then it will clear the wp-cache and avoid activating the Google Sitemap plugin for each post.
- [Related Posts for Jerome's Keywords](http://sw-guide.de/wordpress/plugins/jeromes-keywords-related-posts/) - Plugin which makes it possible to get other posts with similar tags. Haven't started using this myself, but it supports ver. 1.9 and the BETA version of Jerome's Keywords.
- [Fixing Jerome’s Keywords and WordPress 2.1](http://www.arnebrachhold.de/2007/03/03/fixing-error-bug-in-jeromes-keywords-and-wordpress-2-1) - Seems when using Jerome’s Keywords with WP 2.1 then posts looses tags when approving comments for the post.