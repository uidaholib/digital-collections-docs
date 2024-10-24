---
section: Creating Collections
nav_order: 6
title: Publish
---

As you work on your collection branch, be sure to [Commit your changes and Push regularly](https://collectionbuilder.github.io/cb-docs/docs/repository/commit/#commit--push-changes).
Note, the first time you push a new branch to GitHub, the message from GitHub Desktop or VS Code will be about "publishing" your branch--this will make it available on GitHub.
Use meaningful commit messages to ensure collaborators (and your future self) understand what you were doing. 

Using your local server, test your collection in your browser clicking on links and all pages to ensure features are working as expected and all items are displaying.
Often, exploring the collection will point out issues in the metadata that you will want to go back and fix--this is an iterative process!

Do not hesitate to reach out for help debugging issues! 

{% include alert.html text="Please note, when creating a new collection, it will NOT be in the central search index until final publishing. In the meantime, it will use the static Lunr search." color="info" %}

## Publish

Once the collection is ready, submit it to the CDIL team via the [Collection Update Form](https://forms.office.com/r/8S0dZ8viDJ).

[Collection Update Form](https://forms.office.com/r/8S0dZ8viDJ){:.btn .btn-lg .btn-outline-success}

The Digital Projects Manager and Digital Initiatives Librarian will prep it for publication:

- [Merge any updates from main]({{ '/content/maintainers/merging.html' | relative_url }}) if necessary.
- QC metadata fields, config files, about page, and any customizations.
- Ensure ["config-search-index.csv" is correctly configured]({{ '/content/maintainers/search.html' | relative_url }}).
- Test locally.
- Build and deploy to live web location.
- Send collection to DC QC process.
- Add to Search Sources, opt into central-search, and redeploy.
- Guide collection into launch checklist.
