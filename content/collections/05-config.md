---
section: Creating Collections
nav_order: 5
title: Configure
---

In your new collection branch, the first step is to [add your metadata CSV to "_data"](https://collectionbuilder.github.io/cb-docs/docs/metadata/uploading/).

Next, edit the ["_config.yml"](https://collectionbuilder.github.io/cb-docs/docs/config/) with your collection information. 

The "_config.yml" in our template is customized and does not exactly match the standard CB version. 
Pay attention to these options:

- Do not change "url", "source-code", or "digital-assets"
- Update "baseurl" following the pattern: `/digital/collectionstub`
- Create a "title", "tagline", "description", and "keywords"
- Update "metadata" to your CSV's name, which should be the collection stub

## Preview Locally

Now that your metadata and "_config.yml" are set, you will want to start previewing your collection using Jekyll's local server.

Follow the instructions to [Generate Site on cb-docs](https://collectionbuilder.github.io/cb-docs/docs/repository/generate/).
With your server running, you can make changes and it will automatically rebuild. 
Refresh your browser to see the results!

## Continue Configuration

Check the [Theme Options](https://collectionbuilder.github.io/cb-docs/docs/theme/) and [Page Configs](https://collectionbuilder.github.io/cb-docs/docs/customization/) to continue customizing your site to the unique metadata in your collection.

Ensure that you have set a "featured-image" in "theme.yml"!
If your collection does not contain images, try to find a relevant image in our collections or other openly licensed source.

## Write Interpretive Content

Finally, please ensure that the placeholder content on the "about.md" file is replaced. 
Check the [Interpretive Pages cb-docs](https://collectionbuilder.github.io/cb-docs/docs/pages/interpretive/) for more information on editing the file, and our [formatting tips for our conventions]({{ '/content/collections/07-about.html' | relative_url }}).
