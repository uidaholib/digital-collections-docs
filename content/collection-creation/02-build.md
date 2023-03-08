---
section: Collection Creation
nav_order: 2
title: Preview Changes
---

## Developing Locally 

Before serving/building your project for the **first time**, open terminal in the repository root and run `bundle install`. 
The Gem "bundler" will manage dependencies based on the project's "Gemfile", and generate a new "Gemfile.lock" with the full list of dependencies being used.
From then on, you will use `bundle exec` to prefix Jekyll commands to ensure you are using the bundled dependencies.

When developing the collection locally, use `bundle exec jekyll s` to start the development server.
Jekyll will serve the site at the local host url so the links will look like `http://127.0.0.1:4000/demo/psychiana/`.

In the background, Jekyll generates the site and outputs the files to the "_site" directory in your project repository.
Ruby provides a development server from that location.

By default the Jekyll environment is "development" when using `jekyll s`. 
In this environment CollectionBuilder skips some template elements to cut down on build time, including these `_includes`:

- head/item-meta
- head/page-meta
- head/analytics