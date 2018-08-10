## Search engine optimization (_SEO_)

### SEO by wiki

res: [https://en.wikipedia.org/wiki/Search_engine_optimization]()

- Organic / natural / unpaid way to be crawled by search engines
- Used to increase website traffic or to be found often at search results

### SEO for starters by google

res: [https://support.google.com/webmasters/answer/7451184?hl=en]()

- Why? to have a web crawler friendly website

#### Some good practices by google

- Using robots.txt
- Blocking sites you don't want web crawler to crawl
- Use good title tag
- Use description meta tag, _...a good and brief description_
- Wise use of headings
- Use [**structured data**](https://developers.google.com/search/docs/guides/intro-structured-data) _... another topic for another day folks_ - this is the special search engine results in google like it can show the image, schedule, say when it's closed, the star rating, etc...

#### SEO enhancements

[https://developers.google.com/search/docs/guides/search-gallery]()

#### Managing appearance in google results

- Organize site hierarchy

  - include both `http` and `https` versions of your sites
  - include both `www.example.com` and `example.com` version of your sites

- Navigation is important

  - folder structure
  - use of breadcrumbs - its like e.g. `home > contact > social media`

- Use text for navigation

  - avoid script/plugin based navigation
  - avoid images
  - create an **XML Sitemap** for search engines

- Show useful 404 pages

  - put a `noindex` tag on 404 - don't include it on search engines

- Friendly urls

  - e.g. `www.baseballcards.com/article/top-ten-cards.html`
  - avoid too generic pages `folder1`

- Interesting content

  - Avoid almost duplicate content

- Use links wisely

  - Good link text - descriptive

- When using external widgets use `nofollow` meta tags to avoid links provided by widgets

  - e.g. `<meta name="robots" content="nofollow">`

- Use `nofollow` for spam comments - comments section are usually filled with spams (_lol they learned from youtube_)
  - e.g. `<a href="http://www.example.com" rel="nofollow">Anchor text here</a>`

#### SEO friendly Images

- Use `alt` attribute

  - brief and concise

- Use [XML image sitemap](https://support.google.com/webmasters/answer/178636)

- Use standard image formats
  - JPEG
  - GIF
  - PNG
  - BMP
  - WebP

#### Mobile Friendly sites

- Mobile SEO strategies

  - [Responsive Web Design](https://developers.google.com/search/mobile-sites/mobile-seo/responsive-design)
    - Use of `meta name="viewport"` to inform html to adjust
  - [Dynamic Serving](https://developers.google.com/search/mobile-sites/mobile-seo/dynamic-serving)
    - Changing response depending on the user-agent
  - [Separate URLs](https://developers.google.com/search/mobile-sites/mobile-seo/separate-urls)
    - the use of `m.website.com`

- Google's [mobile friendly tester](https://search.google.com/test/mobile-friendly)

- Google's [mobile friendly guide](https://developers.google.com/search/mobile-sites/)

#### Promoting your site

- Having blog traffic
- RSS feeds

#### Analyzing search performance and user behaviour

- Use [google search console](https://www.google.com/webmasters/tools/home)
