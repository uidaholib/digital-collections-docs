---
section_id: Collection Creation
nav_order: 6
title: Create a Collection
---

{% capture template %}
**Metadata Template**

Just starting a collection? Use this [metadata template](https://docs.google.com/spreadsheets/d/1dRgG-Xd28gRZ9ErbU6-1YtgNM6gHFEh3IFNOwKzpoRc/copy?usp=sharing).
{% endcapture %}

{% include alert.html text=template color="info" %}

## Steps for Creating a New Collection With CB-CSV

### Prep
- In your metadata spreadsheet, create objectids for your collection items, use one word (such as `tabor` for Tabor Photograph Collection) + three zeros (ex: `tabor000`)
- Make sure your jpegs and pdfs are all together in one folder, ready to be added to the repository

#### Content Advisory

If there are images that are offensive or may be triggering for users, turn on a content advisory feature by opening the _data/theme.yml file and giving the "content-alert" variable the value true.

You will also need to add a new column to your metadata titled "sensitive". For every photo that you would like to be blurred in the collection, add the value `yes` to its "sensitive" field.

### Create Derivatives
- Navigate to the [collectionbuilder-csv-template](https://github.com/uidaholib/collectionbuilder-csv-template) repo on GitHub
- In the branch dropdown, create a new branch with name based on the collection name you used in your objectid (`tabor`). Use only lowercase letters for branch name, preferably one word.
- In GitHub Desktop, fetch and pull the changes to the collectionbuilder-csv-template repository.
- Switch to the new branch you just created, and open it in Visual Studio Code.
- In the base of the repository, create an `objects` folder and add the collection's digital objects to it.
- In the terminal, run the command `rake generate_derivatives`. This will create `thumbs` and `small` folders inside your `objects` folder, inside of which you'll find newly-created thumbs and smalls of the collection objects.

### Place Objects on Server
- On the library web server, navigate to /digital/objects/, and create a new folder based on the name you gave to the collection's objectids and GitHub branch (in this case, the folder name is `tabor`).
- Make sure that the `rake generate_derivatives` task is complete before doing the following steps.
- Copy and paste the full sized objects from your repository's `objects` folder into this new `tabor` folder.
- Copy and paste the `thumbs` and `small` folders (along with their new content) from your repository's `objects` folder into the new `tabor` folder.
- Delete the `objects` folder from your repository.

### Add Object Paths to Metadata
- Return to your metadata spreadsheet in Google Sheets, and add the following fields if they are not present already: `display_template`, `object_location`, `image_small`, `image_thumb`. Use Google Sheets formulas to fill out these fields based on the objects' formats and their location on the library web server. Use the following resources for help with this:
    - Example metadata (do not edit!): https://docs.google.com/spreadsheets/d/1nN_k4JQB4LJraIzns7WcM3OXK-xxGMQhW1shMssflNM/edit?usp=sharing
    - Metadata Guidelines: https://collectionbuilder.github.io/cb-docs/docs/metadata/csv_metadata/#object-detail-fields-strongly-suggested