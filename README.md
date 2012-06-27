Jekyll RSS Feed Templates
=========================

A few Liquid templates to use for rendering RSS feeds for your Jekyll blog.  Featuring four kinds of feeds:

- **feed.xml** &mdash; Renders the 10 most recent posts.
- **feed.category.xml** &mdash; Only renders posts for a specific category. This example renders posts for a "miscellaneous" category.
- **feed.links.xml** &mdash; Only contains posts that link to external websites noted by a <code>link</code> variable in the [YAML Front Matter](https://github.com/mojombo/jekyll/wiki/YAML-Front-Matter).  Not a common Jekyll convention, but a good way to generating a linked list.
- **feed.articles.xml** &mdash; Only showing articles that don't link to external sites; The opposite of <code>feed.links.xml</code>.

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

This makes it easy to reference the title, description and URL for your site in the feed templates using <code>{{ site.name }}</code>, <code>{{ site.description }}</code> and <code>{{ site.url }}</code>.  Even if you're not using these feed templates, you might find these variables useful when you're designing your layouts.

Note on YAML Front Matter block
------
The xml files contain a [YAML Front Matter](https://github.com/mojombo/jekyll/wiki/YAML-Front-Matter) block with the line <code>layout: none</code>. This is necessary because Jekyll will not process a page with Liquid unless there is a YAML block at the top of the file.
