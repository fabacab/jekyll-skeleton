# Your Website

This folder, called the "web root" or sometimes "document root," contains the whole of your Website. Everything needed to publish your site's HTML pages, [blog posts](_posts/), [events](_data/README.md#events), [gallery](_data/README.md#gallery), [images](static/images/), and more are somewhere within this folder structure. Not all of these files are Web pages. Some are [configuration files](#site-configuration), [data files](_data/README.md#the-_data-folder), or [snippets of templates](_includes/README.md#the-_includes-folder).

The software used to publish your Website is called [Jekyll](https://jekyllrb.com/). It is the program responsible for processing the files in this folder structure and transforming them into the HTML pages, RSS feeds, iCalendar feeds, and other machine-readable formats that your Web browser, news reader, calendaring application, and other client software downloads. Much of the [documentation provided by the Jekyll project](https://jekyllrb.com/docs/) is therefor very useful in understanding both the folder hierarchy contained herein and the contents of each file in these folders.

The rest of this document offers a basic overview of these files, what they do, and how to edit them.

# Folder structure

All [Jekyll projects share a similar folder structure](https://jekyllrb.com/docs/structure/). (In Jekyll's documentation, the term "folder" and "directory" are interchangable.) The most important folders for your website are:

* [`_posts`](_posts/) - Blog posts are saved here.
* [`_data`](_data/) - Site-specific content, such as navigation menus and calendar events, are saved here.
* [`static/images`](static/images/) - Upload images for your blog posts, gallery, etcetera into this folder.

There are other folders as well, but these are the ones you will need to open and edit most often.

# Site configuration

Settings that affect the whole of your website are written to the main configuration file, called [`_config.yml`](_config.yml), located in the document root (this folder). The configuration file itself is written in a highly structured format called [YAML](https://en.wikipedia.org/wiki/YAML). If you edit this file to update a site setting, be sure to change only the setting you intend, and not the structure of the file (i.e., don't change the indentation or remove any punctuation).

One exception to this rule is the human-language text contained in the file. These sections are always prepended with the octothorpe (`#`) character. The octothrope signifies the start of a comment. Such comments are intended to make remembering how to edit the file a little easier. Feel free to edit these comments as you wish.

The remainder of this section describes the individual site settings in greater detail.

## Site settings

Some settings affect almost every page on your website. These settings are documented next.

### `title`

The title of your website. This is shown in the Web browser's title bar, set as the default name for a bookmark, and in numerous places on your site's published web page(s).

### `description`

Your website's description should be a one or two sentence explanation of what your site is for and what a visitor might find useful about it. The description field is sometimes shown in the detail view of search engine result pages, and when someone shares your website address on social media.

### `timezone`

The default timezone for your website. This setting will affect things like the publication dates of blog posts and the specific times of published events. Jekyll uses the `tz` database for understanding timezone information. Set this to the closest city listed in [the `tz` list](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones#List).

For example, for a website whose authors and events are primarily or only located in New York City, New York, United States:

```yaml
timezone: "America/New_York"
```

### `main_logo`

The filename of your website's main logo. To be useful, there must be a file of the same name in your website's [`static/images`](static/images/) folder. For example:

``` yaml
main_logo: my-site-logo.jpg
```

## Build settings

These settings affect the way Jekyll processes your site's source files. You probably shouldn't change any of these. :)

### `markdown`

This setting instructs Jekyll which Gem to use to parse and transform Markdown files. The default, `kramdown`, is the best option in most cases.

### `exclude`

This setting instructs Jekyll to ignore specific files or folders when processing your website. Any path listed in this setting will *not* become a published Web page.

The following example will prevent the file or folder named `vendor` and the file named `README.md` from appearing as a Web page on your published site:

```yaml
exclude:
    - vendor
    - README.md
```

## Blog settings

These settings affect your blog post listing pages and the blog posts themselves.

### `paginate`

How many posts per page should appear on blog listing pages, such as the main blog page, category pages, tag pages, archive pages, and so on.

See also [Jekyll's documentation about pagination](https://jekyllrb.com/docs/pagination/).

### `paginate_path`

This setting determines the URL structure ("pretty permalinks") for paginated pages.

See also [Jekyll's documentation about pagination](https://jekyllrb.com/docs/pagination/).

### `date_format`

The default format for dates.

### `time_format`

The default format for times.

## RSS feed settings

An [RSS ("Really Simple Syndication") feed](http://www.whatisrss.com/) allows visitors to subscribe to your blog posts in news reader applications. This means they can include your site in personalized news feeds (a digital equivalent of a "morning newspaper"). The same technology also allows other websites to automatically syndicate your posts on their own websites. This is often used for automatically sharing event announcements or other news from one site to another.

The RSS feed settings are all contained inside an `rss` object. So, for instance, the [`rss.items`](#rssitems) setting is written as an indented item in YAML like this:

```yaml
rss:
    items: 5
```

### `rss.items`

This setting controls how many of your most recent blog posts to publish in your syndicated news feed. This is similar to [the `paginate` setting](#paginate), but only applies to news feeds.

### `rss.update_period`

This setting is a request to any subscribers of your news feeds to please fetch an update in the specified period. The valid values are:

* `hourly`
* `daily`
* `weekly`
* `monthly`
* `yearly`

The default value is `daily`.

This setting works in tandem with [the `rss.update_frequency` setting](#rssupdate_frequency), described next.

### `rss.update_frequency`

This setting is a request to any subscribers of your news feeds to please fetch an update a certain number of times within the aforementioned [`rss.update_period`](#rssupdate_period). For instance, if this setting is set to `2` and the `rss.update_period` setting is set to `weekly`, your site is asking subscribers to "please fetch an update two times every week."

The default value is `1`.

### `rss.ttl`

Short for "Time To Live," this setting tells subscribers how many minutes the content in the news feed should be considered fresh for. After the `ttl` number of minutes, subscribers should feel free to re-fetch the news feed. Well-behaved subscribers will not refresh the feed before the time to live has expired.

The default value is `60` minutes.

### `rss.editor_email`

The email address of the person responsible for editorial content on the blog. This may or may not not be the same as a blog post's author. You should ordinarily set this to the "admin name" email address in your domain name registration.

### `rss.webmaster_email`

The email address of the person responsible for any technical issues with the news feed. You should ordinarily set this to be the same as your website's "technical contact" email address in your domain name registration.

### `rss.image`

The path to a picture representing your blog content, such as your site logo or a larger version of your website's [favicon](https://simple.wikipedia.org/wiki/Favicon). This must be an [image uploaded to your website](static/images/README.md).

## Page defaults

The `defaults` object in your site configuration controls the default values of certain metadata that accompany your pages.

> TK-TODO: Document some of these? It's not likely going to be changed.
