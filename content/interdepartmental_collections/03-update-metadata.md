---
section: Interdepartmental Collections
nav_order: 3
title: Update Metadata
---

## Updating Metadata for Live Collections

If you need to make some substantial edits to metadata or add new records for a collection that's already live, it’s often easiest to do this in Google Sheets, then re-add the metadata to your repository (note that we strongly recommend you use Google Sheets rather than Microsoft Excel. CollectionBuilder requires that CSV metadata be in UTF-8 encoding, and Excel cannot correctly export a CSV in UTF-8 encoding).
The steps below walk through this process.

### Open Repository and Locate Metadata on Computer

- If this is your first time editing a collection, be sure to clone [collectionbuilder-csv-template](https://github.com/uidaholib/collectionbuilder-csv-template) and [collectionbuilder-cdm-template](https://github.com/uidaholib/collectionbuilder-cdm-template) repositories to your computer following the steps below. If you've already cloned the repositories in the past, skip to the next step.

    - Go to the repositories linked above, and make sure you're logged into GitHub.

    - For each repository, locate the green "Code" button on towards the top right of the GitHub repository window and click on it to expand the drop down. Select the option to "Open with GitHub Desktop." This will clone the repository to your computer and enable you to access it from GitHub Desktop.

- Locate your repository branch name in the [Collection Updates](https://vandalsuidaho.sharepoint.com/:x:/r/sites/Storage-Library/Documents/shared/Digital%20Collections%20Team/Collection%20Updates.xlsx?d=w6432809351bc4863bc70f4517fd61067&csf=1&web=1&e=tHwT3j) spreadsheet. Note whether it is in collectionbuilder-csv-template or collectionbuilder-cdm-template. 

- Back in the GitHub Desktop window, use the top left drop down button to switch your current repository to collectionbuilder-csv-template or collectionbuilder-cdm-template, depending on which one your branch is in.

- Using the middle drop down button, switch to your desired branch.

- Click the "Fetch Origin" / "Pull Changes" button to the right of the branch drop down, to pull any changes and ensure that you're working with the latest changes to the branch.

- Select the "Open in Visual Studio Code" button in the middle of the GitHub Desktop interface or in the top menu click on "Repository > Open in Visual Studio Code." This will open your desired branch in Visual Studio Code.

- Locate and expand the _data folder. Inside will be your desired metadata csv (in most cases will match the collection branch name). Right click on the metadata csv and select "Open in File Explorer" (on Windows) or "Open in Finder" (on Mac).

- Leave your File Explorer / Finder window open to the metadata csv (**but don't open the csv itself!**) and switch to a browser for the next step.

### Open Google Sheets

- In your web browser, open Google Drive. On the left side of the screen, locate the "+ New" button. Click this button. From the drop-down, select Google Sheets. This will open a new Google Sheets document.

- In your new Google Sheet, click File > Import. A white box with four tabs will appear. Select the tab labeled "Upload". This brings up a large box with the words "Drag a file here" above a blue button labeled "Select a file from your device".

- Locate your metadata csv that you located in your File Explorer / Finder in the previous step and without opening it drag it to the Google Drive Upload prompt.

- The CSV will now upload to Google Sheets. At this point, a new box will appear on your Google Sheets screen titled "Import file". Make sure that the correct file is listed under "File". Leave the "import location" and "separator type" dropdowns as they are. Uncheck the box next to "Convert text to numbers, dates, and formulas". Click the "Import data" button.

- Your metadata will now populate your new spreadsheet. Make your edits in the spreadsheet.

{% include alert.html color="success" text="**Tip**: To look at metadata item-by-item in the digital collection website, go to your collection's Browse page. Click on any browse card to get to an item page. In the URL of the item page, locate the item's objectid (the unique identifier located at the end of the item page URL). Look back at the first record in the Google Sheet and locate that record's objectid. Back in the browser, replace the objectid at the end of the URL with the objectid that you found in the first record in the metadata. From this item page, you can press the right browse arrow to navigate through items by objectid, and follow along sequentially in your metadata spreadsheet." %}

{% include alert.html color="danger" text="**Find an object that needs to be deleted?** Always check with the Digital Collections Team Lead before deleting any objects from a collection, even in the case of duplication. If there is a duplicate object in both negative and photograph format in the collection, keep the negative." %}

### Download Metadata from Google Sheets

- To download your metadata from Google Sheets:

    - Click "File" and select "Download as Comma-separated values"

    - Locate the metadata CSV you’ve just downloaded on your computer (probably in the "Downloads" folder!) — but don’t open it!

- *Without opening it* (to avoid issues with Excel scrambling your UTF-8 encoding), ***rename this file the exact same filename as your current collection metadata CSV***.

- Open your collection repository in Visual Studio Code. Locate the _data folder.

- Drag the CSV you just downloaded and renamed from your File Explorer / Finder and drop it directly into the _data folder that you see in Visual Studio Code. Since you gave it the same filename as your previous metadata file, Visual Studio Code will give you the message "A file or folder with the name ‘demo_metadata.csv’ already exists in the destination folder. Do you want to replace it?". Select "Replace" (remember, Git tracks changes, so you can always see the older iterations of your metadata in your commits history and go back to them if you need them).

### Preview Your Changes

- Open your collection repository in Visual Studio Code.

- Open Visual Studio Code's terminal by pressing `ctrl` + `~` (alternately, click on "Terminal" in the Visual Studio Code menu at the top of your window, and select "New Terminal").

- Within the terminal, type `bundle exec jekyll s` (if you're in a collectionbuilder-csv-template branch) or `jekyll s` (if you're in a collectionbuilder-cdm-template branch) and press enter. Copy the server address that the terminal outputs and open it in a browser window. 

- Look through the demo site to make sure everything is working correctly.

- When you're satisfied that the changes are correct, stop the server (`ctrl` + `c`)

### Push Your Changes

- Commit and push your changes using either GitHub Desktop or the command line or Visual Studio Code.

### Submit Collection Update Form

- When you're ready for your changes to be made live, submit the collection to the [Digital Collection Update Form](https://uidaho.co1.qualtrics.com/jfe/form/SV_eRuiZXzEVFKGGF0).

### Make Changes Live (Digital Projects Manager Only)

- Run the `rake deploy` command

- Once the site is finished building, copy over *all of the files* to the site's folder on the webserver

- Check the live site to be sure that everything is functioning correctly