---
section: Creating Collections
nav_order: 7
title: Review
---

As you work on your collection branch, be sure to [Commit your changes and Push regularly](https://collectionbuilder.github.io/cb-docs/docs/repository/commit/#commit--push-changes).
Note, the first time you push a new branch to GitHub, the message from GitHub Desktop or VS Code will be about "publishing" your branch--this will make it available on GitHub.
Use meaningful commit messages to ensure collaborators (and your future self) understand what you were doing. 

## Before Submitting Your Collection

- Ensure there is a point person for the collection. The point person will lead a collection through the review and launch process. Discuss at DC Team if necessary to clarify.
- Checking your metadata:
    - Make sure [format](https://collectionbuilder.github.io/cb-docs/docs/metadata/gh_metadata/#format), [type](https://collectionbuilder.github.io/cb-docs/docs/metadata/gh_metadata/#type) and [display_template](https://collectionbuilder.github.io/cb-docs/docs/metadata/csv_metadata/#display_template) are filled in and assigned appropriately. 
    - Ensure items use the appropriate object type (i.e. documents are PDFs, photographs are JPGs). For example, if an image contains text that should be accessible to users and searchable, it should probably be a PDF with OCR rather than an image file.
- [Check your formatting conventions](https://collectionbuilder.github.io/cb-docs/docs/metadata/formatting/#formatting-your-metadata):
    - Make sure all of your multi-valued fields (subject, author, etc.) use a semi-colon to separate values
    - Strip any leading or trailing white space
    - Make sure your CSV is exported with UTF-8 encoding (default of Google Sheets and OpenRefine. Can not be created by Microsoft Excel)
    - Check that your filenames match your media, including case and file type variations (jpg vs. jpeg vs. JPG)
- [Generate your site on your using your local server](https://collectionbuilder.github.io/cb-docs/docs/walkthroughs/csv-walkthrough/#13-run-the-bundle-exec-jekyll-serve-command-to-generate-your-site-video-version), check links and all pages to ensure features are working as expected and all items are displaying.
- Write descriptive blurb for outreach and launch.

Do not hesitate to reach out for help debugging issues or if you need a batch of images to be converted to PDF with OCR!

{% include alert.html text="Please note, when creating a new collection, it will NOT be in the central search index until final publishing. In the meantime, it will use the static Lunr search." color="info" %}

## Submit for Review

Once the collection is ready for review, submit it to the CDIL team via the [Collection Update Form](https://forms.office.com/r/8S0dZ8viDJ).

[Collection Update Form](https://forms.office.com/r/8S0dZ8viDJ){:.btn .btn-lg .btn-outline-success}
