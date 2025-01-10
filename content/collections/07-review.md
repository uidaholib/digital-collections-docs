---
section: Creating Collections
nav_order: 7
title: Review
---

As you work on your collection branch, be sure to [Commit your changes and Push regularly](https://collectionbuilder.github.io/cb-docs/docs/repository/commit/#commit--push-changes).
Note, the first time you push a new branch to GitHub, the message from GitHub Desktop or VS Code will be about "publishing" your branch--this will make it available on GitHub.
Use meaningful commit messages to ensure collaborators (and your future self) understand what you were doing. 

## Before Submitting Your Collection

- Checking your metadata:
    - Make sure [format](https://collectionbuilder.github.io/cb-docs/docs/metadata/gh_metadata/#format), [type](https://collectionbuilder.github.io/cb-docs/docs/metadata/gh_metadata/#type) and [display_template](https://collectionbuilder.github.io/cb-docs/docs/metadata/csv_metadata/#display_template) are filled in and assigned appropriately. 
    - Ensure items use the appropriate object type (i.e. documents are PDFs, photographs are JPGs). For example, if an image contains text that should be accessible to users and searchable, it should probably be a PDF with OCR rather than an image file.
- [Check your formatting conventions](https://collectionbuilder.github.io/cb-docs/docs/metadata/formatting/#formatting-your-metadata):
    - Make sure all of your multi-valued fields (subject, author, etc.) use a semi-colon to separate values
    - Strip any leading or trailing white space
    - Make sure your CSV is exported with UTF-8 encoding (default of Google Sheets but not Microsoft Excel)
    - Check that your filenames match your media, including case and file type variations (jpg vs. jpeg vs. JPG)
- [Generate your site on your using your local server](https://collectionbuilder.github.io/cb-docs/docs/walkthroughs/csv-walkthrough/#13-run-the-bundle-exec-jekyll-serve-command-to-generate-your-site-video-version), check links and all pages to ensure features are working as expected and all items are displaying.
- Write descriptive blurb for outreach and launch.

Do not hesitate to reach out for help debugging issues or if you need a batch of images to be converted to PDF with OCR!

{% include alert.html text="Please note, when creating a new collection, it will NOT be in the central search index until final publishing. In the meantime, it will use the static Lunr search." color="info" %}

## Quality Control and Publish

Once the collection is ready for review, submit it to the CDIL team via the [Collection Update Form](https://forms.office.com/r/8S0dZ8viDJ).

[Collection Update Form](https://forms.office.com/r/8S0dZ8viDJ){:.btn .btn-lg .btn-outline-success}

The Digital Projects Manager and Digital Initiatives Librarian will prep it for QC and publication:

- [Merge any updates from main]({{ '/content/maintainers/merging.html' | relative_url }}) if necessary.
- Ensure objects and metadata are fully prepped and organized (CDIL Team): 
    - Derivatives generated. 
    - In archive drive for preservation, with README. 
    - On libobjects for access.  
- Ensure ["config-search-index.csv" is correctly configured]({{ '/content/maintainers/search.html' | relative_url }}).
- Test locally.
- Build and deploy to live web location. 
- Once the new collection is online (but unlisted), share the link and blurb out to DC team with a one week timeline for testing and feedback. [Feedback form](https://forms.office.com/r/bBCydjisx3).
- Fix any issues, editing, or ideas that come up from DC-QC.
- Add to [Search Sources, opt into central-search, and redeploy](https://github.com/uidaholib/cdm-migration-project-docs/blob/main/redeploy-with-new-search.md#set-up-search).
- Add an entry to the [Digital Collection Tracking](https://vandalsuidaho.sharepoint.com/:x:/r/sites/Storage-Library/Documents/shared/Teams/Digital%20Collections%20Team/resources/Digital%20Collections%20Tracking.xlsx?d=w08ce4fe4218b4f14ae565732a4e0c44e&csf=1&web=1&e=TQqacd) spreadsheet.  
- Add to collection master list, update "digital_home" and redeploy (to publish to Collection Browse).
- Ensure [Digital Collection Tracking](https://vandalsuidaho.sharepoint.com/:x:/r/sites/Storage-Library/Documents/shared/Teams/Digital%20Collections%20Team/resources/Digital%20Collections%20Tracking.xlsx?d=w08ce4fe4218b4f14ae565732a4e0c44e&csf=1&web=1&e=0xJqMm) spreadsheet is updated, moving collection from “current” to “finished” tab. Record launch date so that we can check on analytics for referrers and spike in use.
- Follow up with Launch Checklist.
