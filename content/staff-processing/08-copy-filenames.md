---
section: Staff Information
nav_order: 8
title: List File Names
---

See the [File Naming](({{ '/content/scanning/02-filenaming.html' | relative_url }})) page in the Scanning section of this site for how to determine a file name structure.

## Generate a list of file names from a directory in File Explorer

- On your PC, open File Explorer and navigate to the folder of files for which you want to capture filenames. 
- Right click on the folder in File Explorer, then select "Git Bash Here," which opens up a terminal view already located in the specified folder. 
- Type `ls > ls.txt` in the command line, which creates a list of all files in the folder in a new file named ls.txt, which is will appear automatically inside the current folder.
- Note that the ls.txt file includes itself as a file in its list, so you’ll need to be sure to delete that row from the generated list. 