---
section: Creating Collections
nav_order: 0
title: Templates Overview
---

Most U of I digital collections are generated from one of our digital collection templates. These templates are based on [CollectionBuilder-CSV](https://github.com/CollectionBuilder/collectionbuilder-csv), but contain customizations and branding specific to the U of I Library. Using the templates allows us to more easily manage consistent look and feel, branding, and updates across collections, while still allowing customization and unique content.

## Digital Collection Templates

Current templates are divided into a set of content specific groups. Although built from the same base, these templates are intended to diverge with features and styles specific to each content type.

- [base-digital-collections-template](https://github.com/uidaholib/base-digital-collections-template) - our generic standard template, used for collections that are mostly images.
- [documents-digital-collections-template](https://github.com/uidaholib/documents-digital-collections-template) - document-centric customizations for collections that are mostly documents.
- [campus-collections-template](https://github.com/uidaholib/campus-collections-template) - U of I campus focused collections.
- [ijc-collection-template](https://github.com/uidaholib/ijc-collection-template) - customizations for International Jazz Collections.
- [oral-history-collections-template](https://github.com/uidaholib/oral-history-collections-template) - base enhanced with OHD features.
- *possible:* community collections? collections originating with partner collections? (priest lake, lchs, potlatch)

## Template Use and Guidelines

Most digital collections are generated from a template repository following these conventions: 

- The `main` branch is a generic base (not a collection itself). The main branch is updated, and updates are merged into collection branches.
- Each collection is represented as a branch in a template repository.
- Collection branch name, libobjects folder name, website folder name, and metadata csv filename should all be the same (if possible), matching the web location stub.
    - e.g. for "https://www.lib.uidaho.edu/digital/aers/", the stub is "aers", thus the branch is "aers", libobjects folder "aers", and metadata is "aers.csv".
- In branches all customizations should be made by creating new layouts or display templates to avoid issues with updating.
- "digital-collections-team" and "digital-maintainers" teams should have write access to all template repositories. **Do not add individual collaborators**, add members to the teams instead (this makes it easier to maintain access).
- Digital objects are *never* committed into the templates.

Some digital collections are not created in the main templates:

- Highly customized collections, usually digital scholarship projects with lots of unique content, are generally an individual repository. Most of these repositories are in thecdil organization rather than uidaholib.
- While collaborating with outside people on a project, it should be in its own repository. Once a collection is stabilized in development, it can be move into a template repository if not highly customized. External collaborators should not be given write access to the template repositories.

## Hosting Notes

The templates are hosted on GitHub for collaboration and version control.
However, the digital collection websites and digital objects are not hosted on GitHub.
Each collection is built manually using Jekyll and deployed to our main static web server. 
All digital objects (images, pdfs, etc) are hosted on our libobjects server.

## Retired Templates

These are for reference only:

- [digital-collections-template-cb-csv](https://github.com/uidaholib/digital-collections-template-cb-csv) - transition CB-CSV project, migrated.
- [collectionbuilder-cdm-template](https://github.com/uidaholib/collectionbuilder-cdm-template) - CONTENTdm collections, migrated.
- [collectionbuilder-csv-template](https://github.com/uidaholib/collectionbuilder-csv-template) - out of date CB-CSV
- [collectionbuilder-sa-spec-exhibits](https://github.com/uidaholib/collectionbuilder-sa-spec-exhibits) - defunct, migrated.
- [collectionbuilder-csv-spec-exhibits](https://github.com/uidaholib/collectionbuilder-csv-spec-exhibits) - defunct, migrated.
