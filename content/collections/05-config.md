---
section: Creating Collections
nav_order: 5
title: Configure
---

In your new collection branch, the first step is to [add your metadata CSV to the "_data" folder](https://collectionbuilder.github.io/cb-docs/docs/metadata/uploading/).

Next, edit the ["_config.yml"](https://collectionbuilder.github.io/cb-docs/docs/config/) with your collection information. 

The "_config.yml" in our template is customized and does not exactly match the standard CB version. 
Comments in the file help explain how to fill in the fields.
Pay attention to these options:

- Do not change "url", "source-code", or "digital-assets"
- Update "baseurl" following the pattern: `/digital/collectionstub`
- Create a "title", "tagline", "description", and "keywords". 
    - Please keep in mind that these values will be used in machine markup and data derivatives--use plain text only! Do not add formatting or links.
    - Keywords are general subjects for the full collection. Apply multiple separating by semicolon `;`, including spaces so it is readable, e.g. `Idaho; Forestry; Recreation`.
- Update "metadata" to match your metadata CSV's name
    - the CSV name should be the same as the collection stub. Do not include ".csv"!

## Preview Locally

Now that your metadata and "_config.yml" are set, you will want to start previewing your collection using Jekyll's local server.

Follow the instructions to [Generate Site on cb-docs](https://collectionbuilder.github.io/cb-docs/docs/repository/generate/).
With your server running, you can make changes and it will automatically rebuild. 
Refresh your browser to see the results!

Web browsers like to cache content which can make it confusing if you are changing things but nothing happens.
For best results, open your test site in a private window, incognito window, or temporary profile.

## Continue Configuration

Check the [Theme Options](https://collectionbuilder.github.io/cb-docs/docs/theme/) and [Page Configs](https://collectionbuilder.github.io/cb-docs/docs/customization/) to continue customizing your site to the unique metadata in your collection.

Ensure that you have set a "featured-image" in "theme.yml"!
If your collection does not contain images, try to find a relevant image in our collections or other openly licensed source.

## Write Interpretive Content

Finally, please ensure that the placeholder content on the "about.md" file is replaced. 
Check the [Interpretive Pages cb-docs](https://collectionbuilder.github.io/cb-docs/docs/pages/interpretive/) for more information on editing the file, and our [formatting tips for our conventions]({{ '/content/collections/06-about.html' | relative_url }}).

The About page should describe the context of the collection content, where the material comes from, and any background on the project.
They can cite sources, explain content details (such as extent or missing items), and acknowledge contributors.

## README

If a collection is highly customized, has ongoing processes for updates, or other information that should be noted--please create a file following the pattern "README-collectioname.md" at the root of the project. 
Put your notes in that file and commit to the branch. 
