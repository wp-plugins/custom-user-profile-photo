=== Plugin Name ===
Contributors: 3five, VincentListrani
Donate link: 
Tags: custom profile photo, user profile, profile photo, user profile photo
Requires at least: 3.6.1
Tested up to: 4.2.2
Stable tag: 0.3
License: GPLv2 or later
License URI: http://www.gnu.org/licenses/gpl-2.0.html

Add a customized User Profile photo to a WordPress user profile.

== Description ==

A more flexible way to attach and display a photo for a WordPress user profile.

Some users might not have or want to have a gravatar account or other universal avatar account. They simply may want to use a one-time specified photo to represent them on your WordPress site. This plugin solves that use case.

With the ability to upload a photo to a user profile via the WordPress Media Uploader or by specifying an external URL to an image, your users and/or authors can have a personalized photo specific to your website.*

By utilizing the WordPress Media Uploader, you also have the ability to use and of the predefined images sizes that the media uploader creates and any custom images size specific to your theme.

This plugin will add a custom set of fields to the user profile page which will allow for the use of a custom profile photo.

You can add/change/edit uploaded photos directly from the user profile page. The external option allows you to provide a URL to the external image or remove it.

**To use this plugin, you will need basic to intermediate WordPress theme development skills. It *does not* overwrite a theme's gravatar/avatar settings.**

Simply go to the users section and select a user. The new fields are added to the bottom of the user profile page. Choose which type of photo you want to use. Upload or add the url, depending on your option. Then press the Update Profile button.

To retrieve the photo on the front-end use the following example on your template page(s):
`<?php
	// Retrieve The Post's Author ID
	$user_id = get_the_author_meta('ID');
	// Set the image size. Accepts all registered images sizes and array(int, int)
	$size = 'thumbnail';

	// Get the image URL using the author ID and image size params
	$imgURL = get_cupp_meta($user_id, $size);

	// Print the image on the page
	echo '<img src="'. $imgURL .'" alt="">';
?>`
You will need to place the code above in each area of your theme where you wish to add or overwrite your theme's gravatar/avatar image. This can include but is not limited to single.php, page.php, and comments.php.

*Future Updates to this plugin include full WordPress avatar integration (posts and comments), allowing other roles to access this feature, and ajax processing of images that use the WordPress Media Uploader.

== Installation ==

1. Upload `custom-user-profile-photo` folder to the `/wp-content/plugins/` directory
2. Activate the plugin through the 'Plugins' menu in WordPress
3. Place `<?php get_cupp_meta($user_id, $size); ?>` in your templates

== Frequently Asked Questions ==

= How do I retrieve the image after I've updated the user profile? =

You can call it in your template page(s) like so: `<?php echo get_cupp_meta($user_ID, $size); ?>`
where the $user_ID is the users ID number and the size is a registered image size like 'thumbnail' or an array like `array(50,50)`

= Who can upload and manage these images? =

Currently, only a user with admin privileges can manage this option.

= I installed the plugin but it doesn't show the new image anywhere. What gives? = 

The plugin does not overwrite the default WordPress gravatar/avatar image. You need at least basic to intermediate WordPress theme editing skills. Please reference the code snippet above or on the Description tab. 

== Screenshots ==

1. The new fields that are added to the user profile page.

2. After uploading and saving your selected image.

3. On hover, Edit or Remove an uploaded image.

4. On hover, Remove a URL to an external image.

5. An example of getting this new image to display on the front-end.

== Changelog ==

= 0.3 =
* Changed the function which gets the attachment post ID by GUID to the WordPress core function attachment_url_to_postid() for better reliability. (Props to sqhendr).

= 0.2.7 =
* Added Hungarian Translation (Thanks to Harkály Gergő)

= 0.2.6 =
* Fixed a bug where the save function required a different capability than the upload function (courtesy of douglas_johnson).

= 0.2.5 =
* Tested with WordPress v4.1
* Fixed a bug where the external URL option would not return the URL with get_cupp_meta().
* Fixed a bug where the saved image did not correspond to the selected radio button.
* Replaced depricated update_usermeta with update_user_meta.
* Improved image selection functionality.
* Images now show immediately after selecting an uploaded item or entering an external URL.
* Added Dutch translation - Thanks Olaf Lederer

= 0.2.4 =
* Tested with WordPress v3.8
* Updated description text. Better explanation of how to quickly use this plugin.

= 0.2.3 =
* Beta version release.

== Upgrade Notice ==

= 0.2.6 =
Bug Fixes and minor improvements.

= 0.2.5 =
Bug Fixes and minor improvements.

= 0.2.3 =
Beta Release