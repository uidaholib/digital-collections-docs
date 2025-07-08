---
section: Updating Collections
nav_order: 2
title: Using Sheets
---

For major updates to metadata, it is generally easiest to do the editing in Google Sheets (rather than directly in VS Code).
Rather than using existing copies of the metadata in Sheets, in most cases it is best to start from a fresh version to avoid running into versioning issues. 

*Note: the version of the CSV in the collection branch is considered the authoritative copy of the metadata.*

## Get Fresh Metadata

1. Open the template repository in VS Code or GitHub Desktop
2. Switch to the collection branch (using VS Code or GitHub Desktop)
3. Git Pull to ensure you have the most up to date code
4. Look in the "_data" folder for the metadata CSV. It should be named the same as the branch (and collection stub). 

## Import to Sheets

1. Go to your [Google Drive](https://drive.google.com/) (logged in as your professional work account!)
2. Open a new blank Sheets
3. Click File > Import 
4. On the modal, click Upload. Browse to the "_data" folder of the template repository or drag and drop the metadata CSV from the repository.
5. On the next modal, select import location: "Replace spreadsheet" (or "Insert new sheet"), separator type: "Comma", and UNCHECK "Convert text to numbers, dates, and formulas". Then click "Import data".

## Edit in Sheets

Be safe and have fun!

Note: for published collections **NEVER change or renumber objectid's**! Once a collection is published, the objectid forms the URL to the Item page and are considered permanent reference links. Changing objectid's will break any existing references.

## Export from Sheets

1. Click File > Download > "Comma Separated Values (.csv)"
2. Look in your computer's Download folder for the file. Do NOT double click (by default this will open it in Excel, which will corrupt your characters)! 
3. Rename the CSV file to exactly match the existing metadata

## Add to Collection Branch

1. Copy the downloaded CSV into the "_data" folder in the template repository, replacing the old copy
2. Check the git diff to see if the changes are what you expected
3. Test on local server, `bundle exec jekyll s`
4. Commit your changes (with a meaningful message!) in VS Code or GitHub Desktop
5. Push to GitHub (from VS Code or GitHub Desktop)

## Deploy

Notify the CDIL team via [Collection Update Form](https://forms.office.com/r/8S0dZ8viDJ) to publish to live web!
