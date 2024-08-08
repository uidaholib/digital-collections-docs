---
section_id: Interdepartmental Collections
nav_order: 8
title: Collection Templates
---

Most U of I digital collections are generated from one of our digital collection templates.
These templates are based on [CollectionBuilder-CSV](https://github.com/CollectionBuilder/collectionbuilder-csv), but contain customizations and branding specific to U of I Library.
Using the templates allows us to more easily manage consistent look and feel, branding, and updates across collections, while still allowing customization and unique content.

## Current Digital Collection Templates

Current templates are divided into a set of content specific groups.
These templates are intended to gradually diverge with features and styles specific to each content type over time.

- [ijc-collection-template](https://github.com/uidaholib/ijc-collection-template) - International Jazz Collections
- [campus-collections-template](https://github.com/uidaholib/campus-collections-template) - highlighted campus collections
- [base-digital-collections-template](https://github.com/uidaholib/base-digital-collections-template) - general collections (photographs)
- [documents-digital-collections-template](https://github.com/uidaholib/documents-digital-collections-template) - for document-centric collections
- [oral-history-collections-template](https://github.com/uidaholib/oral-history-collections-template) - base enhanced with OHD features
- *possible:* community collections? collections originating with partner collections? (priest lake, lchs, potlatch)

## Template Use and Guidelines

Most digital collections are generated from a template repository following these conventions: 

- The `main` branch is a generic base (not a collection itself). The main branch is updated, and updates are merged into collection branches.
- Each collection is represented as a branch in a template repository.
- Collection branch name, libobjects folder name, website folder name, and metadata csv filename should all be the same (if possible), matching the web location stub.
    - e.g. for "https://www.lib.uidaho.edu/digital/aers/", the stub is "aers", thus the branch is "aers", libobjects folder "aers", and metadata is "aers.csv".
- In branches all customizations should be made by creating new layouts or display templates to avoid issues with updating.
- "digital-collections-team" and "digital-maintainers" teams should have write access to all template repositories. **Do not add individual collaborators**, add members to the teams instead (this makes it easier to maintain access).

Some digital collections are not created in the main templates:

- Highly customized collections, usually digital scholarship projects with lots of unique content, are generally an individual repository. Most of these repositories are in thecdil organization rather than uidaholib.
- While collaborating with outside people on a project, it should be in its own repository. Once a collection is stabilized in development, it could move into a template repository if not highly customized.

## Retired Templates

These are for reference only:

- [digital-collections-template-cb-csv](https://github.com/uidaholib/digital-collections-template-cb-csv) - transition CB-CSV project
- [collectionbuilder-cdm-template](https://github.com/uidaholib/collectionbuilder-cdm-template) - CONTENTdm collections
- [collectionbuilder-csv-template](https://github.com/uidaholib/collectionbuilder-csv-template) - out of date CB-CSV
- [collectionbuilder-sa-spec-exhibits](https://github.com/uidaholib/collectionbuilder-sa-spec-exhibits) - defunct, migrated.
- [collectionbuilder-csv-spec-exhibits](https://github.com/uidaholib/collectionbuilder-csv-spec-exhibits) - defunct, migrated.
