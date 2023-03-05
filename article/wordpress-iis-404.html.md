---
title: 'Custom 404 page on IIS with correct http return code'
date: '2008-09-01T22:52:26+02:00'
status: publish
permalink: /article/wordpress-iis-404.html
author: Snakefoot
excerpt: 'Creating a custom 404 page for WordPress running on IIS.'
type: post
id: 770
category:
    - Uncategorized
tag:
    - iis
    - wordpress
post_format: []
tags:
    - 'wordpress,iis'
---
Microsoft Internet Information Server (IIS) supports PHP and MySQL, and therefore it can also run Wordpress. Wordpress prefers Apache as its web-server, which one will notice when trying to use pretty permalinks or other "advanced" features. See [Making Wordpress 2.0 run on IIS](/article/wordpress2-iis.html)  
  
 IIS supports custom error pages, and when configuring a custom 404 page, then it will be activated when Wordpress fails to lookup a page. See [Permalink Validator](http://wordpress.org/extend/plugins/permalink-validator/). The problem is that the custom 404 page must activate the Wordpress engine to maintain the theme.  
  
 Example of a custom 404 page for IIS, that will load the 404 page of the active Wordpress theme (Place it in **wp-content**): `<?phpheader("HTTP/1.1 410 Gone");header('status: 410 Gone');//header("HTTP/1.0 404 Not Found");//header('status: 404 Not Found');define('BBPATH', dirname(__FILE__) . '/' ); // BB-Press integrationif (file_exists('../wp-blog-header.php'))	require_once('../wp-blog-header.php');	global $wp_query;if (isset($wp_query))	$wp_query->set_404();if ( $template = get_404_template() )		include($template);?>` One will notice that the above example code actually returns 410 instead of the proper http return code 404. It seems that some installations of IIS will cause the PHP engine to stop if sending out a 404 return code. Instead one can use the 410, since its meaning is pretty much the same.  
  
 While optimizing the return codes of the Wordpress blog, then one should consider creating a custom page for database errors. By default Wordpress will return the standard http return code 200 if the database is down or overloaded. The proper http return code is 503 (Service unavailable), and will prevent search engines from accepting the database errors as valid content. Wordpress 2.3.2+ makes it easy to create a custom page as it automatically calls **wp-content/db-error.php** if it exists (Older versions of Wordpress requires modification of [wp-includes/wp-db.php](http://allforces.com/2006/06/18/custom-wordpress-errors/))