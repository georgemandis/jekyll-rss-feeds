Jekyll RSS Feed Templates
=========================

**NOTE:** If you're a fan of this project you should checkout the sister project: [jekyll-json-feeds](https://github.com/snaptortoise/jekyll-json-feeds).

A few Liquid templates to use for rendering RSS feeds for your Jekyll blog.  Featuring four kinds of feeds:

- **feed.xml** &mdash; Renders the 10 most recent posts.
- **feed.category.xml** &mdash; Only renders posts for a specific category. This example renders posts for a "miscellaneous" category.
- **feed.links.xml** &mdash; Only contains posts that link to external websites noted by a <code>link</code> variable in the [YAML Front Matter](https://github.com/mojombo/jekyll/wiki/YAML-Front-Matter).  Not a common Jekyll convention, but a good way to generating a linked list.
- **feed.articles.xml** &mdash; Only showing articles that don't link to external sites; The opposite of <code>feed.links.xml</code>

How to use
----------
- Update \_config.yml as noted below, or manually replace the variables.
- Copy one of the xml (ie, <code>feed.xml</code>) files to the root directory of your Jekyll blog.
- Run <code>jekyll</code>.

In your generated <code>\_site</code> folder you should find a properly formatted feed at <code>feed.xml</code>.

Customizing \_config.yml
------
These templates rely on a customized version of <code>\_config.yml</code>.  The following lines have been added:

	name: Your Blog's Name
	description: A description for your blog
	url: http://your-blog-url.example.com
	feed_items: 10
	feed_update_period: daily
	feed_update_frequency: 1

This makes it easy to reference the title, description and URL for your site in the feed templates using <code>{{ site.name }}</code>, <code>{{ site.description }}</code> and <code>{{ site.url }}</code>.  Even if you're not using these feed templates, you might find these variables useful when you're designing your layouts.

The `feed_*` items shown above are the default. You can safely omit them.

Miscellany
-----------
- **Note on YAML Front Matter block**: The xml files contain an empty [YAML Front Matter](https://github.com/mojombo/jekyll/wiki/YAML-Front-Matter) block. This is necessary because Jekyll will not process a page with Liquid unless there is a YAML block at the top of the file. 

- **Note on layouts**: Previously, this block contained the line <code>layout: none</code> but that was found to cause a separate issue for some: https://github.com/snaptortoise/jekyll-rss-feeds/commit/209b83b504fde14722491ea5d9753189566c8598. However, if you've specified a *default* layout in your `_config.yml` file then you **will** most likely want to specify `layout: none` for your RSS feeds. Otherwise they will render in the default layout which is likely to be an HTML page. See this issue for reference: [https://github.com/snaptortoise/jekyll-rss-feeds/issues/32](https://github.com/snaptortoise/jekyll-rss-feeds/issues/32)

- **RSS Autodiscovery**: If your template is not already setup to do so, make sure the RSS feeds are discoverable by browsers, bots, etc. by providing proper link tags to your Jekyll layout files (adapt `href` and `title` appropriately):

    	<link href="/blog/feed.xml" type="application/rss+xml" rel="alternate" title="Latest 10 blog posts (atom)" />

    Refer to [rssboard.org/rss-autodiscovery](http://www.rssboard.org/rss-autodiscovery) for details.
- **Validation**: You can use the W3C Validator to make sure your feeds are formatted correctly: [http://validator.w3.org/feed/](http://validator.w3.org/feed/)

- If you're a [Pinboard](https://pinboard.in) user and found this repo useful, take a look at [jekyll-pinboard](https://github.com/snaptortoise/jekyll-pinboard-plugin). It allows you to load your Pinboard bookmarks into your Jekyll site with just a couple lines.

- If you're looking for [JSON feed](jsonfeed.org) templates to add to your Jekyll blog please checkout the sister project: [jekyll-json-feeds](https://github.com/snaptortoise/jekyll-json-feeds).
