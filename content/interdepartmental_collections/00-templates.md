---
section_id: Interdepartmental Collections
nav_order: 8
title: Collection Templates
---

This guide is intended as a reference for U of I faculty outside of the CDIL (Special Collections, Fellowships, etc). Before following this guide, you will need to [install all of the items specified in the  software](https://collectionbuilder.github.io/cb-docs/docs/software/) section of our main CB docs, including creating a GitHub account and installing a Visual Studio Code.
 
Most U of I digital collections are generated from one of our digital collection templates. These templates are based on [CollectionBuilder-CSV](https://github.com/CollectionBuilder/collectionbuilder-csv), but contain customizations and branding specific to the U of I Library. Using the templates allows us to more easily manage consistent look and feel, branding, and updates across collections, while still allowing customization and unique content.

## Find the Appropriate Template

Current templates are divided into a set of content specific groups:

- [ijc-collection-template](https://github.com/uidaholib/ijc-collection-template) - International Jazz Collections
- [campus-collections-template](https://github.com/uidaholib/campus-collections-template) - U of I campus focused collections
- [base-digital-collections-template](https://github.com/uidaholib/base-digital-collections-template) - majority still image collections
- [documents-digital-collections-template](https://github.com/uidaholib/documents-digital-collections-template) - majority document collections
- [oral-history-collections-template](https://github.com/uidaholib/oral-history-collections-template) - base enhanced with OHD features

## Create A Branch

Once you’ve identified the correct template, open the link to its GitHub page and click the green “Code” button and select “Open with Github Desktop.” This application should prompt you to clone the repository. Once accepted, you will need to create a  branch.

## Naming Conventions

This is where we need to start thinking about metadata. For ease of organization, please name the branch, the items in the collection and object ids with the same name. Please lower case this name and use acronyms when appropriate. For example the **Plant, Soil, and Entomological Sciences** collection can be branch name **pses**, item name **pses_001.jpg** and object id **pses_001**. 

## Visual Studio Code

Once this branch has been created from the `Main`, select the publish tab and then select “Open in Visual Studio Code.” Within VSC, you will be working within the terminal (ctrl+shft+`) within the “shell” of bash (as opposed to PowerShell, Python, etc). To make your default terminal bash, search “integrated shell” in the command palette at the top and select the box for Terminal > Integrated > Shell Integration: Enabled. You should be ready to go!

