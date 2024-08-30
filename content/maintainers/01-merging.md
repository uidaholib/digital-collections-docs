---
section: Maintainers
nav_order: 1
title: Merging Main into Branch
---

The `main` branch of our templates receives updates from CB-CSV and our customizations and fixes. 
These do not automatically get added to collection branches.
Whenever working on a collection (adding content, fixing issues), it is best to first pull in any updates from `main`.

To update a collection you will have to "merge" the `main` into the collection branch.
Note that this is the opposite of typical git workflows, so GitHub tends to not be very helpful with auto suggestions for this process!

## Update main!

First, always make sure your `main` branch is up-to-date, switch to `main` and do a `git pull`.

## Select a branch to update

1. In GitHub Desktop (or VS Code), find the branch you want to update and switch to it.
2. Do a `fetch` and `git pull` to update this branch with any remote changes.

## Merge main branch into the branch you've selected

- GitHub Desktop:
    1. In the Branches dropdown on GitHub Desktop, click the bottom button that says "Choose a branch to merge into [whatever branch you're on]," and choose the "main" branch. Once you select "main," the merge will begin.
    2. In some cases there will be conflicting files, and you'll need to click a button that accepts this to continue the merge.
- Command line:
    1. in VS Code terminal ensure you are on the correct branch `git status`
    2. type `git merge main`
    3. *If there are no conflicts*, merge message will pop up, type Ctrl+X to save default message. If there are conflict, merge will stop and you will have to resolve the conflicts first (edit them in VS Code), then complete the merge commit.

## Sort out merge conflicts

**needs revision** 

GitHub Desktop will list the conflicts you need to resolve before the merge can be committed. To resolve them: 

1. Open the project in VS Code and locate and open a file that GitHub desktop says needs to be resolved. 
2. Scroll down in that file until you see the specific conflict area(s) highlighted, including the old and new content that conflicts. Git directly marks the conflicts in the text file by adding a pattern:
    - The top of the conflict has `<<<<<<< HEAD` on its own line, followed by the content in the old version of the file. 
    - Next you will see a line of `=======`, followed by the content of the new version of the file. 
    - Finally closed by `>>>>>>> branch_name`.
3. VS Code offers tools to try to manage these conflicts: above the highlighted section, you'll see a series of buttons that say `accept current change`, `accept incoming change`, and `accept both`. (Note these buttons are added by VS Code and aren't part of Git).
    - `current change` = changes on the current branch
    - `incoming change` = changes from the main branch
4. Which option you accept depends on which file you're looking at, so always look carefully at the code before determining which change to accept. In many cases, if the file is in the _includes folder, you'll probably accept the `incoming change` option to incorporate general updates to the collectionbuilder template code. If the file is in the _data folder, you'd be more likely to accept the `current change`, since these files are likely heavily customized to fit the collection. This isn't always the case, though, so take care and don't hesitate to reach out to Olivia to confirm. In some cases you might need to `accept both` and then sort it out manually.
5. Once you sort out the conflicts on a file, save the file. When you switch back to GitHub Desktop, you should see that the conflict is resolved, so you can move on to the next conflict following the instructions above.
6. Remember that you can always click on the files you edited in the Changes column of VS Code to see the git diff visualized, so you can review the changes to make sure they are correct.
7. After you've sorted out all the conflicts, you can either make a commit or move onto the changes below, whichever makes the most sense to you. If there are a lot of files that were changed in the merge, it might make more sense to commit at this point, since you'll be changing more in the steps below and it may be hard to keep track of your changes.

## General

1. Serve the site using `bundle exec jekyll s`
2. Click around to test out the site and ensure everything is still working.
3. On the **browse page** and **item pages**, make sure there are no broken links, images not showing up, etc. (if you see something amiss, fix it!)
    - Check the config-metadata.csv in the _data folder (remember, this controls what metadata shows up on the collection's item pages) and compare it with the collection's metadata spreadsheet. Are there any fields you think should be added to the metadata displaying on the collection's item pages? If so, add them to the config-metadata.csv. Make sure any field with browse_link = `true` in the config-metadata.csv is also included on the browse cards, using the config-browse.csv, since the browse links won't work properly if the fields aren't included on the browse cards. 
4. Check to see if the **map** is properly centered and if the **word clouds** make sense.
    - Check theme.yml file to see what metadata fields are included in the locations and subjects word clouds. First, check the metadata CSV to determine if there are any other fields you should add to these visualizations. Second, make sure the same fields are included on the browse cards, using the config-browse.csv, since the word cloud links won't work properly if the fields aren't included on the browse cards. 
5. Check the **timeline** dropdown (top right of the timeline page) and change it in theme.yml if it needs editing. Note that in the "Timeline Page" section of theme.yml, only one of the two variable options (`year-navigation` and `year-nav-increment`) should be used. If you're using `year-navigation`, remember to use quotation marks around your series of dates, just as the example does.

## About Pages

1. Check the About page for content and format, cleaning up and making edits as you see fit, following guidelines on [About Pages docs]({{ '/content/collections/07-about.html' | relative_url }}).
    - In particular, keep an eye out for hyperlinked text that says something like "click here." When you see this, rephrase so that the hyperlinked text describes what it links to, i.e. "For more information, see the [Idaho Forestry Website](https://www.idl.idaho.gov/forestry/)," *not* "To check out the Idaho Forestry Website, [click here](https://www.idl.idaho.gov/forestry/)."
    - Check citations to see if they are in the correct format.
    - Change any full links to pages within the collection to use relative_url. 
    - Consider whether a link should open in a new tab. In the past we regularly used `{:target="_blank" rel="noopener"}`. However, best practices now suggest never opting in a new tab, so they should likely be removed.

## Metadata

### Edit current metadata in Google Sheets

1. Import the collection's metadata csv into google sheets to edit.
2. In most cases, if any column is empty, you can delete that column. 
3. Rename the `reference url` field `cdm_url`
4. Make sure that the column with the URLs to the copyright statements is titled `rightsstatement` (it might say `rights information` or `rights (standardized)`). Change it so it is titled `rightsstatement`.
5. Rename `image/jpg` values to `image/jpeg`
6. Do a general overview to make sure the metadata looks good. If you notice any potential projects, make a note in the collections updates spreadsheet for future work.
7. Export the spreadsheet from google sheets as a csv, and upload to the repository, replacing the old metadata spreadsheet.
8. If you changed any field names, check "theme.yml" and the config- csv files to ensure things still line up.

## Commit and push your changes

Use VS Code and/or GitHub Desktop to commit and push your changes up to GitHub.

## Update the live site

1. Stop the jekyll server (`ctrl` + `c`) and run the command `rake deploy`. This might take a few seconds to generate, depending on how big the collection is. When you see a "done" message in the terminal, this process is finished and you can move to the next step.
2. Locate the template repository in your file explorer and navigate to the `_site` folder (you can also easily do this from VS Code by right clicking the `_site` folder and selecting "Reveal in File Explorer"). (Note: **you *must* be sure to only copy files from the _site folder**. Files outside of this folder will not be configured correctly for our server, and you'll notice right away that the site does not work.)
3. Leaving this file explorer window open, proceed to open another file explorer window. In this one, select the `Websites (W:)` drive. Select www-lib-uidaho-edu > Content > digital > the collection folder you want to update (in most cases, this folder name will match the branch name. If you don't see this folder name, check the record for the collection in the digital_all_collections spreadsheet).
4. Carefully copy and paste the content from your repository "_site" folder into the collection folder. As soon as you copy these files over, they will be live. (Ctrl+A = select all; Ctrl + C = copy; Ctrl + V = paste)
5. Check the live site *in a private window or incognito window* to make sure everything looks correct. Click around to test the site.

## Update the digital_all_collections spreadsheet

1. Update the value for the `last_cb_update` field in the digital_all_collections spreadsheet (located in the uidahodigital Google Drive, in AdminCollections folder) to reflect the current year and month.

## Update the Collection Updates spreadsheet

1. If a new collection, add a new collection row to the [Collection Updates](https://vandalsuidaho.sharepoint.com/:x:/r/sites/Storage-Library/Documents/shared/Digital%20Collections%20Team/Collection%20Updates.xlsx?d=w6432809351bc4863bc70f4517fd61067&csf=1&web=1&e=ncx3hD) spreadsheet in the Digital Collections Team Sharepoint folder and add the current date to the "Date updates went live" column. If updating a current collection, find the collection's row in the same spreadsheet and add the current date to the "Date updates went live" column.
