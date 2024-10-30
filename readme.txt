=== In Over Your Archives ===
Contributors: stresslimit, whatch, cvernon, batmoo
Tags: inoveryourhead, julien smith, archives, archive, posts, jquery
Requires at least: 2.9.2
Stable tag: 1.4.3

This plugin will display your archive page in a nice way, just like on <a href="http://inoveryourhead.net/archive">inoveryourhead.net</a>.

It was a collaboration between <a href="http://stresslimitdesign.com">stresslimit</a> and <a href="http://inoveryourhead.net">Julien Smith</a>.

== Description ==

This plugin will display your archive page in a nice way, just like on inoveryourhead.net

== Installation ==

1. Extract the contents of the zip file into your `/wp-content/plugins/` directory
2. Activate the plugin through the 'Plugins' menu in WordPress
3. You can either create an archive page with a template that includes the code `<?php echo ioya_archive(); ?>`, or create a page with the shortcode `[ioya]`
4. Enjoy!

== Other Notes ==

= Shortcode filtering =

If you are using the In Over Your Archives shortcode [ioya] to embed the plugin on a page and would like to do category filtering on 
your archive results, you may do so by providing the category slug(s) or ID(s), (or a mix) like so:

`
[ioya cat='trees']
[ioya cat='03,45']
[ioya cat='trees,45,trucks']
`

= Customizing the template =

You can customize the look and feel of the archives pages.

Add a file called `ioya_month.php` to your theme directory and add a basic loop in it as follows:

`
<?php while (have_posts()) : the_post(); ?>
    
    <div class="post">    
		<div class="date">
        	<div class="date-day"><?php the_time('j') ?></div>
            <div class="date-month"><?php the_time('M') ?></div>
        </div>
        <h2><a href="<?php the_permalink() ?>" rel="bookmark" title="Permanent Link to <?php the_title_attribute(); ?>"><?php the_title(); ?></a></h2>
        <small>Posted by <?php the_author_link() ?> at <?php the_time('g:i A') ?></small>
        <div class="entry">
        	<?php the_excerpt(); ?>
        </div>
    </div>
<?php endwhile; ?>
`

Then modify as necessary.

== Screenshots ==

1. The archive as implemented on inoveryourhead.net
2. This is the colour customization in the admin section

== Changelog ==

= 1.4.3 =
* small bug fixes

= 1.4.2 =
* small bug fixes

= 1.4.1 =
* implemented shortcode filtering by category.
* various tweaks and performance improvements

= 1.4 =

* Mainly Javascript optimizations. 
* Fixed a few bugs:
** broken links to prev / next years

= 1.3.1 =

* Bug introduced in the previous update was loading all posts across all pages

= 1.3 = 

* Added filters so you can change the number and size of the image thumbnails displayed
* Bug Fixes:
** Various errors
** Archive page now shows all posts; they were being limited to your site's posts per page count.

= 1.2 =

* More bug fixes!
** fixed a bug where imagecreatefromstring() in wp core was being called on empty string
** fixed a bug where in certain cases we wouldn't get any thumbnails at all
** better handling when we are in a month with no posts, so we jump to the month before
** a bunch of small optimization stuff

= 1.0.1 =

* Various release-related bug fixes:
** updated css to prevent months from displaying on multiple lines
** added the ability to provide a list of images to ignore, if you use small "utility" images like itunes buttons, get by email, twitter, etc
** improved the parsing function which finds images automatically
** fixed a css bug where month abbreviations were being split onto 2 lines

= 1.0 =

* Initial release

== Frequently Asked Questions ==
