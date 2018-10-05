# Contentful notes

**Special Terms**

- Space - new content project that will hold all your data.

  - new space, new api keys, new space id

- Space ID - Unique ID, used for authentication, aside from API keys

## Starter Guide

res: [https://www.contentful.com/blog/2018/04/09/foolproof-guide-getting-started-contentful/?utm_campaign=new-org-activate&utm_medium=in-app&utm_source=intercom&utm_content=foolproof-getting-started&utm_term=]()

**starter files**: [https://github.com/christineywang/product-catalogue/blob/master/cf-product-catalogue-starter.zip]()

### How to access the API

You need these set of credentials:

- space ID - you'll see it in the dashboard.

- Access Token / API keys - also in the dashboard. Don't share / upload it to github. There are 2 types, preview and content tokens. Basically, access to see, and access to modify content

- Content type ID - This is like the table name identifier, if you think of your content as tables in databases.

## Designing your content model

### Normalize

Think of your content as like designing SQL tables. E.g. Product, you have brands and categories, which is another table again.
