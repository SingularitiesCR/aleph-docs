# Aleph Documentation

We use [Jekyll](http://jekyllrb.com/) to build our documentation site using **Markdown**, and we host it by pushing the code to [GitHub Pages](http://pages.github.com/).

> This repository is exclusively for the **Aleph Documentation**.

## Jekyll theme

The Jekyll Theme used for this documentation was **Edition Jekyll Template** develop by **CloudCannon** and it can be found in [this repository](https://github.com/CloudCannon/edition-jekyll-template).

## Pre-requirements

1. Ruby (*If you are developing in OSX, install* ***Ruby*** *with RVM instead of Homebrew to avoid issues with some gems*)
2. Bundler (*A Ruby gem*)

## Setup

1. Clone this repository.
2. On the root of the project run `bundle install`.

To generate the files locally and preview them, run `bundle exec jekyll serve`.

> The **Pull Request** should be merge to a version branch instead of the **master** branch.

## Add Content

To add content to the documentation site:

1. Under the folder `_docs`, select a category to add new content or create a new one.
2. Create a documentation page using **Markdown**.
3. Use, at least, the following **Front Matter** configuration.

```yaml
---
title: Title of the page
category: Category
order: 1 # The index of the page
---
```

4. Create a new post in `_posts` with the name *"YYYY-MM-DD-title"*. It must specify the author and what was added.
5. Generate the files to preview them.
6. If it generates as expected, create a **Pull request** to add the content.


## Updates

1. Select a **Markdown** file from the `_docs` folder.
2. Update its content.
3. Create a new post in `_posts` with the name *"YYYY-MM-DD-title"*. It must specify the author, what was updated and the type of the update(*major or minor*).
4. Generate the files to preview them.
5. If it generates as expected, create a **Pull request** to update the content.

