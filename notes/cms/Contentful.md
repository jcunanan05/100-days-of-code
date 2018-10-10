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

## Reference Fields and Content Type

res: [https://www.contentful.com/r/knowledgebase/content-modelling-basics/#the-basics]()

These are the heart of the CMS. Since this is a innovative CMS as they say, they said to throw off your old knowledge of what a CMS is.

Contentful says: "Your content doesn’t have to be fit into our model – instead, you make the model to fit your content"

### When to use multiple spaces

Use multiple spaces when:

- When you have a different project
- Testing playground

### Content Type

Think of Content Type as a Header. You'll assign fields here, or even another content type.

e.g. You have a content type: `Post`, it has `content` field, `title` field, and an `Author` content type. An Author content types contains fields related to the author.

### Duplicate and Delete Content types

You can only delete content types if you empty its contents. It's a restraint that contentful put so you can't accidentaly remove a content type.

### Disabled Fields

Disabled fields means this can't be fetched. It might be project status or something.

#### Deleting Fields

You must disable it first. It's contentful's way of avoiding it to be deleted by accident
