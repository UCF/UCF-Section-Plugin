# UCF Sections #

Provides a custom post type, shortcode and functions for displaying Sections.


## Description ##

Adds a new post type called Sections that can be added to pages using a `[ucf-section]` shortcode. Sections will display content from within the WordPress editor.

The `[ucf-section]` shortcode has several options:
* `slug` - the slug of the section to be displayed
* `id` - the ID of the section to be displayed (as an alternative to providing the `slug` attribute)
* `class` - CSS class(es) to assign to the generated `<section>` element. By default, sections will always have the `.ucf-section-SLUG` class assigned to them.
* `title` - a descriptive title to use both as an accessible `aria-label` value for screenreaders in the generated `<section>` element, and in navbar links generated by the [Automatic Sections Menu Shortcode](https://github.com/UCF/Section-Menus-Shortcode).
* `section_id` - a value to assign as the `ID` attribute of the generated `<section>` element.
* `random_from_tag` - if provided a tag slug, a random section will be chosen to display from sections that are assigned the given tag.


## Installation ##

### Manual Installation ###
1. Upload the plugin files (unzipped) to the `/wp-content/plugins` directory, or install the plugin through the WordPress plugins screen directly.
2. Activate the plugin through the "Plugins" screen in WordPress

### WP CLI Installation ###
1. `$ wp plugin install --activate https://github.com/UCF/UCF-Section-Plugin/archive/master.zip`.  See [WP-CLI Docs](http://wp-cli.org/commands/plugin/install/) for more command options.



## Changelog ##

### 1.1.3 ###
Enhancements:
* Modified filtering options for files that are selectable from the media library modal when choosing a CSS or JS file for a page/post.  Both CSS and JS will now be filtered by their respective file extensions by default (to filter out other files with the `text/plain` type), CSS filtering now includes the `text/plain` type, and JS filtering now includes the `text/javascript` type.
* Updated packages.

### 1.1.2 ###
Bug Fixes:
* Updated npm packages
* Fixed an issue where get_post_sections() throws notice
* Added responsive images with wp_make_content_images_responsive()

### 1.1.1 ###
Bug Fixes:
* Ensure that styles and scripts are loaded when using random shortcode attribute

### 1.1.0 ###
Enhancements:
* Added `random_from_tag` shortcode attribute and logic that enables a random section to be displayed from the given tag slug
* Upgraded packages and gulpfile
* Added linter configs, Github issue/PR templates, and CONTRIBUTING doc to repo

### 1.0.15 ###
Bug Fixes:
* Updated logic and provided an additional help function for processing sections in content outside of the main post_content

### 1.0.14 ###
Bug Fixes:
* Added null check to suppress a warning that was bring thrown.
* Added logic to handle non-content sections.

### 1.0.13 ###
Bug Fixes:
* Updated critical syntax error that prevented sections from being able to be displauyed on their template pages.

### 1.0.12 ###
Enhancements:
* Various changes to the way front end assets are enqueued for sections for faster loading.

### 1.0.11 ###
Bug Fixes:
* Corrected a minor issue with a regex.

### 1.0.10 ###
Enhancements:
* Updated section plugin to automatically add the text from the first heading it finds into an `aria-label` attribute on the section.

### 1.0.9 ###
Bug Fixes:
* Disabled archives by default.

### 1.0.8 ###
Bug Fixes:
* Added missing CSS and JS file upload capability out-of-the-box

### 1.0.7 ###
Bug Fixes:
* Fixed some notices thrown by `UCF_Section_Common::get_post_sections()` when the global `$post` object is not available (e.g. on category/tag archives, or when a 404 is returned).

### 1.0.6 ###
Enhancements:
* Added missing plugin description
* Updated available shortcode attributes in readme

### 1.0.5 ###
Enhancements:
* Added unique classes to sections
* Added `role` and `aria-label` attributes to sections that provide a title
* Updated `UCF_Section_Common::get_post_sections()` to use the current `$post` object if `$post` is a section, allowing section-specific css/js to be loaded in `single-ucf_section.php` theme templates.

Bugfixes:
* Added missing `data-section-link-title` attributes to sections for compatibility with the Sections Menu Shortcode Plugin.

### 1.0.4 ###
Enhancements:
* Added stylesheet and javascript field for sections
* Added mechanism for enqueuing the stylesheets to section specific tags in the head
* Added mechanism for enqueuing the javascripts to section specific tags in the footer

### 1.0.3 ###
Enhancements:
* Added the ability to add css classes to the section wrapper.
* Added the ability to define the id of the section wrapper.
* Added the ability to add a title to the section wrapper (which can be used in templates to define the menu text).

### 1.0.2 ###
Bug Fixes:
* Corrects incorrect sections being returned when providing a slug instead of an id.

### 1.0.1 ###
Bug Fixes:
* Fixes [#2](https://github.com/UCF/UCF-Section-Plugin/issues/2) by parsing `$labels` args and setting them to variables.
* Fixes [#1](https://github.com/UCF/UCF-Section-Plugin/issues/1) by renaming the non-existent `$output` variable to `$before`, `$content` and `$after` respectively.
* Adds additional comments.

### 1.0.0 ###
* Initial release


## Upgrade Notice ##

n/a


## Installation Requirements ##

None


## Wishlist/TODOs ##
* None
