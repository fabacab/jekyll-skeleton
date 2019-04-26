# The `_data` folder

This folder contains [Jekyll data files](https://jekyllrb.com/docs/datafiles/), which are used for controlling certain contents in your website. This includes files for ordering the navigation menus, images in the gallery, and for working with and publishing event information to your Web pages and other applications. It contains a number of different types of files (see [§ Files in this folder](#files-in-this-folder)) including both published artifacts and work-in-progress.

1. [Files in this folder](#files-in-this-folder)
1. [Contact Info](#contact-info)
1. [Gallery](#gallery)
1. [Navigation menus](#navigation-menus)
1. [Opening Hours](#opening-hours)

## Files in this folder

* `README.md` - This help file. :)
* [`contact_info.yml`](#contact-info) - Your contact information, such as you telephone number and physical address.
* [`gallery.yml`](#gallery) - Description of which images to display on your site's gallery, and in what order.
* [`opening_hours.yml`](#opening-hours) - Listing of your business's opening hours.
* [`nav_menus.yml`](#navigation-menus) - Description of which pages to link to from the navigation menus.

## Contact Info

It is easy to change the contact information displayed on your website simply by changing the content of this file. Each line in this file contains a part of your contact information. For example:

```yml
---
street_address: 123 Main Street
extended_street_address: Unit 2
locality: Pleasantville
region: NY
postal_code: 12345

telephone: +1-555-123-4567
email: mybusiness@example.com
```

Each line is relatively self-explanatory, in that the line that begins with `email: ` determines your main contact email address. To change your email address, simply change the email address value.

## Gallery

Your site includes a customizable gallery. To add an image to your site's gallery, first upload the image to [your site's `static/images` folder](../static/images/). Once uploaded, it can be referenced from [the `gallery.yml` data file](gallery.yml) (in this folder). By editing the `gallery.yml` file, you can control which uploaded images are included in your website's gallery, write captions for the images, make the images into clickable links, and more.

The `gallery.yml` file is written in a structured format called [YAML](https://en.wikipedia.org/wiki/YAML). When you edit YAML files, be careful to maintain the structure of the file (i.e., match the indentation and punctuation style as in the rest of the file).

Your gallery images are represented as a single YAML list. Each item in the list (a dash on its own line) represents an image in the gallery. Each image in the gallery has, at a minimum, an `image` field, whose value should be the name of an image file in [your site's `static/images` folder](../static/images/). You may also specify the following optional fields for each image:

* `alt` - Brief textual description of the image, usually no more than a sentence or two. For example, `Sunset on a sand beach over calm waters.` This text is usually not displayed visually but provides a [gracefully degrading fallback](https://en.wikipedia.org/wiki/Fault_tolerance) in case of a network error, as well as [important accessibility benefits](https://en.wikipedia.org/wiki/Wikipedia:Manual_of_Style/Accessibility/Alternative_text_for_images) for browsers with visual impairments, including humans as well as bots.
* `caption` - A caption for the image. This accompanies the image as visually rendered text somewhere near the image itself. HTML is allowed in this field.
* `link` - A Web address (URL) to use as the destination of the link this image will become. Omit this field if you do not want the image to be a link.
* `link_title` - The `title` attribute text of the image's link. This text is usually displayed as a tooltip when a visitor hovers their mouse cursor over the image. This field is ignored unless `link` is also set.
* `featured` - Whether or not the image should be included on the front ("home") page. The only valid value is `true`; omit this field if you do not want to include the image on the front page.
* `object_position` - Used to tweak the cropped position of non-standard image dimensions.

## Navigation menus

[The `nav_menus.yml` data file](nav_menus.yml) defines the name, order, and contents of your site's navigation menus. Each menu has a name, such as `main` or `sidebar`. Each menu is a list of links that may also be an image. At a minimum, each menu item must include a `url` and a `text` field.

Optionally, menu items may also include the following fields:

* `title_text` - The `title` attribute's text for the link.
* `image` - The name of an image file in [your site's `static/images` folder](../static/images/). Omit this field to create a textual navigation menu item.

## Opening hours

The [`hours.yml`](hours.yml) file is where you can edit your business's opening hours. This file contains lines that look like

```yml
sunday: 8am - 5pm
monday: 7am - 5pm
```

and so forth. Simply edit the approriate line to change what your website publishes.

