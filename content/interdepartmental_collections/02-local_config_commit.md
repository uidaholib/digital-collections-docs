---
section: Interdepartmental Collections
nav_order: 2
title: Developing Locally, Configuration and Committing
---

Before serving/building your project for the **first time**, open terminal in the repository root and run `bundle install`. 
From then on, you will use `bundle exec` to prefix Jekyll commands to ensure you are using the bundled dependencies.

When developing the collection locally, use `bundle exec jekyll s` to start the development server. Jekyll will serve the site at the local host url so the links will look like `http://127.0.0.1:4000/demo/collection_name/`.

In the background, Jekyll generates the site and outputs the files to the `_site` directory in your project repository.
Ruby provides a development server from that location.

## Initial Configuration

Once you have a local version of your site open, you can begin the process of building and configuring the collection. Begin with dropping the CSV of your data into the `_data` folder. If the object path metadata is correct, you should be able to see the items and their associated objects immediately. Next, adjust the config.yml section of the site according to [this guide](https://collectionbuilder.github.io/cb-docs/docs/config/url/). 

## Push Your Changes

Once you have adjusted this initial code and save on these pages, you will see a number pop up on the `source control` icon in VSC. Select this icon and you will see all of the adjusted pages. First, select the add button to move these pages to the staging area, then write a short description for the commit like “config.yml set-up” and then press commit.
