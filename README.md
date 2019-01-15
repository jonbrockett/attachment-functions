# WordPress Attachment Functions
WordPress functions for developers to use instead of wp_get_attachment functions to inline SVGs.

## What It Does ##
Using the new functions will run each image through a check to see if it's an SVG. It'll then output the SVG using the alt tag from the media library for the uploaded image, add role="img", and also sizes it. If it's not an SVG it runs wp_get_attachnment_image or equivalent WP function.

## Instructions ##
You can either include this code directly in your __functions.php__ file in your theme or add to a directory, such as __library/attachment-functions.php__ then include it in your __functions.php__ code:

/\*\* Image functions for attachment images \*/
require_once( 'library/attachment-functions.php' );

## The Functions ##
Use the same as https://developer.wordpress.org/reference/functions/wp_get_attachment_image/
__get_the_image($attachment_id,$size = 'thumbnail', $icon = false, $attr = '')__    Returns the image or inline SVG code
__the_image($attachment_id,$size = 'thumbnail', $icon = false, $attr = '')__    Prints the image or inline SVG code
__get_the_thumbnail_bg($post = null, $size = 'post-thumbnail')__    Returns the thumbnail image or inline SVG code
__the_thumbnail_bg($size = 'post-thumbnail')__    Prints the thumbnail image or inline SVG code
__get_the_image_bg($attachment_id,$size = 'thumbnail', $icon = false, $attr = '')__    If an SVG returns the image as inline SVG CSS code otherwise it returns the image as a URL
__the_image_bg($attachment_id,$size = 'thumbnail', $icon = false, $attr = '')__    Prints the background image SVG inline or image url

A number of other functions that are used internally
__is_svg($attachment_id)__   Returns True/False
__get_svg($attachment_id,$size = 'thumbnail', $icon = false)__    Returns the SVG code
__the_svg($attachment_id)__    Prints the SVG code
__generate_ratio($new_size = array(), $old_size = array())__    Takes a value and returns an array of the width, height (Mainly used to assist __get_the_image()__ when generating the SVG size)
