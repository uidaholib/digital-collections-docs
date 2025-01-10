---
section_id: Creating Collections
nav_order: 8
title: Overview
---

Each Digital Collections consist of several parts:

- Objects: the digitized files such as jpgs, pdfs, mp3s, etc.
- Metadata: the spreadsheet describing the items.
- CollectionBuilder template: a branch in collection template or separate project repository.

This "Creating Collections" section describes the workflow for setting up a new collection using one of our standard templates at U of I library.
The complete process to create a collection from a generic template is described in the [CB-Docs](https://collectionbuilder.github.io/cb-docs/)--this version adds context specific to the workflows of Digital Collection team.

Most Digital Collections team members will not regularly need to complete the full process to create a new collection--many of the steps will be completed by core maintainers, with collaborators focusing on metadata and interpretive content. 

## Overview of the Process

1. Prepare collection objects and metadata.
2. CDIL team loads prepared objects to libobjects server.
3. Select collection template.
4. Create new branch for collection. 
5. Add metadata CSV to "_data" folder.
6. Configure collection's "_config.yml".
7. Configure pages and nav.
8. Write interpretive content in "about.md".
9. Test on local machine (ongoing).
10. Notify CDIL team to publish to live web.
11. DC QC process.
12. Launch!

## Naming Convention

For ease of organization, we follow a naming convention to create an "id" for each collection that will be used for the web location, branch name, and metadata csv name--that we call the collection "stub".
The stub will be all lowercase, no spaces, and no special characters (other than `-`).
Generally it will correspond to an existing identifier, nickname, or acronym as appropriate.

For example, for the "Agricultural Economics Research Series" collection, the stub is "aers", thus the URL is "https://www.lib.uidaho.edu/digital/aers/", the branch is "aers", libobjects folder "aers", and metadata is "aers.csv".
If you are generating objectids for your collection, you can also use the stub as the base, e.g. "aers339".

Select your stub name in consultation with CDIL team and ensure it does not conflict with existing collections!
