---
section: Maintainers
nav_order: 2
title: Deploy
---

Digital Collection Team members will submit information via [Collection Update Form](https://forms.office.com/r/8S0dZ8viDJ) to trigger updates.
When a collection is ready to be published or updated the CDIL team is in charge of deploying the collection to the live web.

The Digital Projects Manager and Digital Initiatives Librarian will prep it for publication/update.
Overview:

1. Switch to the collection branch and git pull to get updates.
2. [Merge any updates from main]({{ '/content/maintainers/merging.html' | relative_url }}) if necessary.
3. QC branch with local testing (see below).
4. Build and deploy to live web location (see below).

For new collections, we will also send the collection to DC QC and launch process.

## QC Branch

Start your local server and look at the branch code to check over details:

- Review metadata fields to ensure current required fields exist, are correctly named, and are filled according to our current conventions. Update legacy fields as necessary. In particular fix these fields which require standardization for aggregation:
    - "title" is not blank.
    - "date" is in ISO format (yyyy-mm-dd, yyyy-mm, or yyyy only, no slashes! Other date styles can be in "archival_date" field).
    - "type" matches standard DCMI Type Vocabulary.
    - "format" matches MIME type standard.
    - "rightsstatement" is a valid URI.
    - "language" is valid 3 letter code.
- Review config files to ensure metadata is being used correctly.
- Carefully check ["config-search-index.csv"]({{ '/content/maintainers/search.html' | relative_url }}) to ensure it will get relevant metadata.
- Review about page to ensure it exists and has relevant content matching our conventions.
- Review any customizations to ensure they are functioning as intended (occasionally legacy content is broken!).

## Build and Deploy

Once QC is complete:

1. Run `rake deploy` in the terminal in the collection branch, wait for it to build (this can take a long time!).
2. In your File Explorer, open the folder containing the collection branch, and navigate to the "_site" folder.
3. In a new File Explorer window, open the Websites drive and navigate to the "digital" folder in Websites > www-lib-uidaho-edu > Content > digital. 
4. Inside the "digital" folder, the collection will have a folder matching it's stub name. If it is a new collection create a new folder using the stub name. Navigate into the collection folder.
5. Inside the "_site" folder, select all (Ctrl+A) and copy (Ctrl+C).
6. Inside the collection folder on the server, paste the files (Ctrl+V). Wait for all the files to transfer over.
7. Open a new private window in your browser and test the collection to ensure everything looks correct.
