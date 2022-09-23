---
section: CollectionBuilder
nav_order: 2
title: CollectionBuilder-CSV
---

# Updating metadata for live collections

## Edit metadata
- Navigate to the collection repository/branch and open it in VS Code
- Locate the metadata file and upload it to google sheets
- Edit the metadata in google sheets
- Download the metadata from google sheets as a CSV
- Add the metadata to the _data folder in VS Code, copying over the previous version of the metadata file

## Double check and make it live
- Run `bundle exec jekyll s` and look through the site to make sure everything is working correctly
- Stop the server (`ctrl` + `c`), and run the `rake deploy` command
- Once the site is finished building, copy over *all of the files* to the site's folder on the webserver
- Check the live site to be sure that everything is functioning correctly


# Building your Collection

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

# Steps for Creating a New Collection

## Prep
- In your metadata spreadsheet, create objectids for your collection items, use one word (such as `tabor` for Tabor Photograph Collection) + three zeros (ex: `tabor000`)
- Make sure your jpegs and pdfs are all together in one folder, ready to be added to the repository

## Create Derivatives
- Navigate to the [collectionbuilder-csv-template](https://github.com/uidaholib/collectionbuilder-csv-template) repo on GitHub
- In the branch dropdown, create a new branch with name based on the collection name you used in your objectid (`tabor`). Use only lowercase letters for branch name, preferably one word.
- In GitHub Desktop, fetch and pull the changes to the collectionbuilder-csv-template repository.
- Switch to the new branch you just created, and open it in Visual Studio Code.
- In the base of the repository, create an `objects` folder and add the collection's digital objects to it.
- In the terminal, run the command `rake generate_derivatives`. This will create `thumbs` and `small` folders inside your `objects` folder, inside of which you'll find newly-created thumbs and smalls of the collection objects.

## Place Objects on Server
- On the library web server, navigate to /digital/objects/, and create a new folder based on the name you gave to the collection's objectids and GitHub branch (in this case, the folder name is `tabor`).
- Make sure that the `rake generate_derivatives` task is complete before doing the following steps.
- Copy and paste the full sized objects from your repository's `objects` folder into this new `tabor` folder.
- Copy and paste the `thumbs` and `small` folders (along with their new content) from your repository's `objects` folder into the new `tabor` folder.
- Delete the `objects` folder from your repository.

## Add Object Paths to Metadata
- Return to your metadata spreadsheet in Google Sheets, and add the following fields if they are not present already: `display_template`, `object_location`, `image_small`, `image_thumb`. Use Google Sheets formulas to fill out these fields based on the objects' formats and their location on the library web server. Use the following resources for help with this:
    - Example metadata (do not edit!): https://docs.google.com/spreadsheets/d/1nN_k4JQB4LJraIzns7WcM3OXK-xxGMQhW1shMssflNM/edit?usp=sharing
    - Metadata Guidelines: https://collectionbuilder.github.io/cb-docs/docs/metadata/csv_metadata/#object-detail-fields-strongly-suggested
