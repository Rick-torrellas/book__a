---
title: "Create a doc"
description: "" 
date: 2022-09-28T18:56:08
tags: [""]
categories: [""]
draft: false
---
Create a Markdown file, [greeting.md](http://greeting.md/), and place it under the docs directory.

```jsx
website # root directory of your site
├── docs
│   └── greeting.md
├── src
│   └── pages
├── docusaurus.config.js
├── ...
```

At the top of the file, specify id and title in the front matter, so that Docusaurus will pick them up correctly when generating your site.

```jsx
---
id: greeting
title: Hello
---

## Hello from Docusaurus

Are you ready to create the documentation site for your open source project?

### Headers

will show up on the table of contents on the upper right

So that your users will know what this page is all about without scrolling down or even without reading too much.

### Only h2 and h3 will be in the TOC by default.

You can configure the TOC heading levels either per-document or in the theme configuration.

The headers are well-spaced so that the hierarchy is clear.

- lists will help you
- present the key points
- that you want your users to remember
  - and you may nest them
    - multiple times

### Custom id headers {#custom-id}

With `{#custom-id}` syntax you can set your own header id.
```

## **Doc tags**

Optionally, you can add tags to your doc pages, which introduces another dimension of categorization in addition to the docs sidebar. Tags are passed in the front matter as a list of labels:

```jsx
---
id: doc-with-tags
title: A doc with tags
tags:
  - Demo
  - Getting started
---
```

**TIP**

Tags can also be declared with `tags: [Demo, Getting started]`.
