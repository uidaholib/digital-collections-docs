---
section_id: Creating Collections
nav_order: 8
title: Intro and Setup
---

Each Digital Collections consist of several parts:

- Objects: the digitized files such as jpgs, pdfs, mp3s, etc.
- Metadata: the spreadsheet describing the items.
- CollectionBuilder template: a branch in collection template or separate project repository.

This "Creating Collections" section describes the workflow for setting up a new collection in Digital Collections using one of our standard templates at U of I library.
Most Digital Collections team members will not regularly need to create new collections or complete the full process--many of the steps will often be completed by core maintainers, with collaborators focusing on objects, metadata, and interpretive content. 

The complete process to create a collection from a generic template is described in the [CB-Docs](https://collectionbuilder.github.io/cb-docs/).

## Setup

### GitHub 

To access the collection templates you will need a [GitHub account](https://collectionbuilder.github.io/cb-docs/docs/software/github/#github-account).
We suggest setting one up with a "professional" non-U of I email account--this ensures you will have access even if you leave U of I, but also not connected to your personal email--if you don't have one, set up a new Gmail account since we often end up on Google Sheets and Docs for work anyway!

Once you have a [GitHub account](https://collectionbuilder.github.io/cb-docs/docs/software/github/#github-account) set up, email your account name to the maintainers to get added to our GitHub organization. 

Our org, [uidaholib](https://github.com/uidaholib) owns all the project repositories to ensure continued access and easy collaboration. 
Digital Collection team members will be added to the [digital-collections-team](https://github.com/orgs/uidaholib/teams/digital-collections-team). 
This team has write access to all the relevant templates and project repositories. 

Using the teams allows us to change membership and manage access with out needing to add/remove individual accounts to every repository--please use the teams and do not unnecessarily add individuals to repositories!

### Software 

To be able to develop and test a collection on your local computer you will need Git, VS Code, Ruby, and Jekyll installed.
To generate image derivatives you will need ImageMagick and GhostScript (not all DC team members will need to do this!).

Please follow the [software install instructions on cb-docs](https://collectionbuilder.github.io/cb-docs/docs/software/).

| Software | Process |
| --- | --- |
| Google Sheets | Create and edit metadata spreadsheets; create CSV |
| Git, GitHub Desktop | Copy the templates to your local and sync work |
| VS Code | Edit the project files |
| Ruby, Jekyll | Test the site locally; build the final site |
| ImageMagick, GhostScript | Generate image derivatives |
| OpenRefine | Bulk transform and improve metadata |
{:.table .table-bordered}
