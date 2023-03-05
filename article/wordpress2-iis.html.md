---
title: 'Making Wordpress 2.0 run on IIS'
date: '2007-01-16T09:05:11+01:00'
status: publish
permalink: /article/wordpress2-iis.html
author: Snakefoot
excerpt: 'Required modifications for Wordpress 2 to make it work on IIS.'
type: post
id: 127
category:
    - Uncategorized
tag:
    - iis
    - wordpress
post_format: []
tags:
    - 'wordpress,iis'
---
Perform the following changes:  
  
 1. Change **REQUEST\_URI** in **wp-settings.php** and add PATH\_INFO (Will make WP-cache work on IIS): `if ( empty( $_SERVER['REQUEST_URI'] ) ) {   $_SERVER['REQUEST_URI'] = $_SERVER['SCRIPT_NAME'] . $_SERVER['PATH_INFO'];` 2. Change **wpdb** in **wp\_db.php** and modify this (Make sure all MySQL tables are using UTF8): `	mysql_query("SET NAMES 'utf8'");	$this->select($dbname);}` 3. Change **get\_archives** in **template\_functions\_general.php**: `	} elseif ('yearly' == $type) { 		$arcresults = $wpdb->get_results("SELECT DISTINCT YEAR(post_date) AS `year`, MONTH(post_date) AS `month`, count(ID) as posts FROM $wpdb->posts WHERE post_date year); 				if ($show_post_count) { 					$text = sprintf('%d', $arcresult->year); 					$after = ' ('.$arcresult->posts.')' . $afterafter; 				} else { 					$text = sprintf('%d', $arcresult->year); 				} 				echo get_archives_link($url, $text, $format, $before, $after); 			} 		}	}` 4. Updated **Classes.php** so the search can handle quoted search: `		// If a search pattern is specified, load the posts that match		if (!empty($q['s'])) {			// added slashes screw with quote grouping when done early, so done later 			$q['s'] = stripslashes($q['s']);			if ($q['sentence']) {				$q['search_terms'] = array($q['s']);			}			else {				preg_match_all('/".*?("|$)|((? 1 && $q['search_terms'][0] != $q['s'] ) $search .= " OR (post_title LIKE '{$n}{$term}{$n}') OR (post_content LIKE '{$n}{$term}{$n}')";			$search = " AND ({$search}) ";		}` 5. Installed the plugin [Atom 1.0 for WordPress](http://benjamin.smedbergs.us/wordpress-atom-1.0/) and changed it so it would allow different feeds and work with IIS: `<link rel="self" type="application/atom+xml" href="<?php echo get_bloginfo_rss('rss2_url'); ?>atom/" />` `global $feed;if (is_feed() && $feed=="atom") {` 6. Added a **httpd.ini** with the following contents: `[ISAPI_Rewrite]# Rules to ensure that normal content gets throughRewriteRule /software-files/(.*) /software-files/$1 [L]RewriteRule /images/(.*) /images/$1 [L]RewriteRule /favicon.ico /favicon.ico [L]RewriteRule /robots.txt /robots.txt [L]# For file-based wordpress content (i.e. theme), admin, etc.RewriteRule /wp-(.*) /wp-$1 [L]# Rules to perform 301 redirect (Remove index.php if already specified)RewriteRule /index.php/(.*) /$1 [I,RP]# For normal wordpress content, via index.phpRewriteRule ^/$ /index.php [L]RewriteRule /(.*) /index.php/$1 [L]` 7. Added a **Robots.txt** with the following contents: `User-agent: *Crawl-delay:30Disallow: /wp-content/Disallow: /wp-includes/Disallow: /wp-admin/Disallow: /xmlrpc.phpDisallow: /wp-trackback.phpDisallow: /wp-settings.phpDisallow: /wp-rss2.phpDisallow: /wp-rss.phpDisallow: /wp-register.phpDisallow: /wp-rdf.phpDisallow: /wp-mail.phpDisallow: /wp-pass.phpDisallow: /wp-login.phpDisallow: /wp-links-opml.phpDisallow: /wp-feed.phpDisallow: /wp-config.phpDisallow: /wp-commentsrss2.phpDisallow: /wp-comments-post.phpDisallow: /wp-blog-header.phpDisallow: /wp-atom.phpDisallow: /wp-commentsatom.phpDisallow: */feedDisallow: */atomDisallow: */rss2Disallow: */rssDisallow: */trackback`