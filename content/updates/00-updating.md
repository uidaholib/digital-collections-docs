---
section_id: Updating Collections
nav_order: 9
title: Overview
---

Updating existing collections is the most common and important work we do, including:
adding new items, bulk refining metadata, updating individual items based on feedback, fixing broken links, or polishing interpretive content.
This section covers working with existing collections.

*Note: the version of the CSV in the collection branch is considered the authoritative copy of the metadata. Be sure to update any copies on Sheets before working on them to avoid versioning issues.*

## Overview of Updating an Existing Collection

1. Find template repository and collection branch, open in VS Code.
2. Git Pull to ensure you have the most up to date code.
3. Edit in the branch
    - For minor metadata edits and fixes: directly edit the metadata CSV in VS Code. Find & Replace is very helpful!
    - For major metadata edits or adding new items: import the CSV into Sheets, edit, then download as CSV and replace the old copy.
    - For content editing: work in VS code. Use Find & Replace to find specific text. Ask questions if you can't find where the content is coming from!
4. Test on local machine.
5. Commit and Push changes.
6. Notify CDIL team via [Collection Update Form](https://forms.office.com/r/8S0dZ8viDJ) to publish to live web.

## Where is the Collection Branch?

When looking at a live digital collection website, right click the page and select "View Page Source".
In the source code, scroll down to the end of the head section.
You will find an html comment that lists which template and branch the collection was built from. 
For example:

```
<!-- Last build date: 2025-01-09
documents-digital-collections-template, metadata: iftnc
https://github.com/uidaholib/documents-digital-collections-template 
-->
```

## Tools

- VS Code - you can edit metadata CSV directly in your text editor, but it is a bit hard to look at! Using "rainbow csv" extension helps. For major edits, you will probably want to use Sheets.
- Google Sheets - used for most metadata creating and editing. 
- OpenRefine - an excellent tool for bulk fixes and transformations of existing metadata. Great for exploring metadata, discovering consistency issues, and combining data. Not for new data entry.
- Excel - generally NOT used. Excel cannot import or export UTF-8 encoding correctly and will corrupt characters. You can create and work on metadata with Excel (for example, because you want to use OneDrive to collaborate with students), however do not attempt to import or export our CSVs with Excel. Use Google Sheets or OpenRefine to create an XLSX file from our existing CSV, then work on the XLSX file in Excel. When ready to deploy, open the XLSX with Sheets or OpenRefine to export the CSV. 

**NEVER use Excel to create CSVs! NEVER use Excel to open CSVs!**
