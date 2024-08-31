---
section: Maintainers
nav_order: 1
title: libobjects
---

"libobjects" is our media server for Digital Collections, and is live at "objects.lib.uidaho.edu".
All digital objects (images, pdfs, etc) are hosted on our libobjects server, rather than the main web server.
This keeps managing the media (lot of storage) separate from the HTML (less storage, more files).

The CDIL team has responsibility to add, update, and manage objects on the server. 
Generally, DC Team members will contact us via the Collection Update Form when new items need to be added. 

Each collection's objects are stored on libobjects in a directory matching the collection "stub". 
Inside each folder is the files (images, pdfs, etc), and usually the "small" and "thumbs" directories containing the image derivatives.

A set of Rake tasks for bulk processing objects is in [rake-utilities-for-digital](https://github.com/uidaholib/rake-utilities-for-digital).
Maintainers should have a copy of this repository on their local machine for working on projects.

## Prep Objects for libobjects

Overview: 

1. QC objects
2. [Generate derivatives](https://collectionbuilder.github.io/cb-docs/docs/objects/derivatives/#generate-derivatives-rake-task) using `rake generate_derivatives`
3. Copy the folder to the libobjects server (in a folder matching the collection name)
4. Copy the full quality objects and metadata to the archive drive (if this has not already been completed)

### QC objects

Check filenames and extensions to ensure they follow conventions and best practices:

- Filenames are all lowercase, no spaces, no special characters (other than underscore `_` or dash `-`).
- Extensions are lowercase and standard spellings.
- Access files are created, e.g. convert TIFFs if necessary or assemble PDFs.
- Review file sizes to ensure they are reasonable, e.g. should be high quality (so low file sizes might be a red flag worth investigating), but not excessively huge (so very large file sizes should be investigated). 

Rename files if necessary (this can be done with Rake tasks, and ensure the metadata is updated as well if necessary).
Optimize or resize files if necessary (Adobe Acrobat for PDFs; Photoshop, [Squoosh](https://squoosh.app/), or ImageMagick for images).

Tip: Your File Explorer / Finder might hide file extensions by default. Check your View settings to show extensions!

### Generate Derivatives

Work in your folder of "rake-utilities-for-digital": 

1. Copy the set of collection files into the "objects" folder in "rake-utilities-for-digital".
2. Open a terminal in "rake-utilities-for-digital" (either open Git Bash in that location or open the folder with VS Code and open a terminal).
3. Type the command `rake generate_derivatives` (this uses the default options which is what we use in 99% of the time, but you can customize if necessary, [check the docs](https://github.com/uidaholib/rake-utilities-for-digital/blob/main/docs/generate_derivatives.md)).
4. Wait for it to run! This might take a long time...
5. When the task completes, there will be a new "small" and "thumbs" folder. Check that those folders contains the same number of images as there are images + pdfs in the collection.

### Move to libobjects

If necessary map libobjects following the map drive instructions and using password in KeePass.

1. Open a file explorer with "libobjects" and navigate to the collection's directory (or create it if it is new).
2. Open a separate file explorer with your prepped objects (the "objects" folder in "rake-utilities-for-digital" from last step).
3. Copy the prepped objects (Ctrl+A = select all; Ctrl+C = copy), then click in the "libobjects" folder and paste them in the collection folder (Ctrl+V = paste).
4. Wait for them to transfer! This might take a long time...
5. When complete, you can test by visiting a link following the pattern `https://objects.lib.uidaho.edu/collectioname/examplefile.jpg`. Let the folks know that the objects are ready!

### Move to archive drive

Check up to ensure all original files and metadata are stored on the archive drive!
The "small" and "thumbs" should not be on the archive drive since we can regenerate them.

If you are adding to archive drive, ensure the folder has:

- a README.md or README.txt with information about the collection.
- metadata
- all original files
