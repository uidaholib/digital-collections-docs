---
section: Creating Collections
nav_order: 1
title: Create Branch
---

To create a new collection you will be adding a branch to one of the collection template repositories. 
This can be done on the GitHub interface or on your local machine.

## Clone a Collection Template 

To work on your local machine, you will need to have a copy of the repository "cloned" to your computer.
This only has to be done once for each repository, so if you already have a copy, you don't need to do it again--skip this step! 

Visit the GitHub link for the template you will be using, then follow the [clone repository steps in cb-docs](https://collectionbuilder.github.io/cb-docs/docs/repository/clone/).

## Create a New Branch

Each collection is contained in a branch, so to start a new one, you will be creating a new branch in the template repository.  

### Naming Convention

For ease of organization, we follow a naming convention to create an "id" for the collection that will be used for the web location, branch name, and metadata csv name--that we call the collection "stub".
The stub will be all lowercase, no spaces, and no special characters (other than `-`).
Generally it will correspond to an existing identifier, nickname, or acronym as appropriate.

For example, for the "Agricultural Economics Research Series" collection, the stub is "aers", thus the URL is "https://www.lib.uidaho.edu/digital/aers/", the branch is "aers", libobjects folder "aers", and metadata is "aers.csv".
If you are generating objectids for your collection, you can also use the stub as the base, e.g. "aers339".

Select your name and ensure it does not conflict with existing collections!

### Create Branch

Open the template repository with VS Code. 

1. Ensure you are on the "main" branch of the repository by looking at the lower left corner of the editor.
2. Ensure your "main" branch is up to date by doing a Git Pull / Sync.
3. Click the branch name "main" in the lower left corner of the editor, which will open up a window at the top with "+ Create new branch" highlighted. Click "Create new branch" (or click enter), then type in the "stub" name you have selected, then press enter.

You are now working in the new collection branch!
