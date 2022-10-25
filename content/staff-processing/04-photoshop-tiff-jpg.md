---
section: Staff Processing Workflows
nav_order: 4
title: Batch Convert Tiff to Jpeg
---

The CDIL preserves the TIF files produced during scanning as archival files, so the TIF files are not edited for color adjustment or visual presentation. An action in Adobe Photoshop is used to run a batch process on the archival TIF files to produce full resolution Jpeg copies that can be cropped and processed. Actions are a series of commands in Photoshop that have been recorded that Photoshop can play back to execute the same commands on different files.

## Photoshop Batch Actions

### Tiff to Access Jpeg Action

- In Photoshop, make sure you have access to the Actions Window by selecting it under the Window menu (Window>Actions) or with the shortcut Alt+F9.

<div class="container">
  <div class="row">
    <div class="col">
{% include figure.html img="PhotoshopWindowMenu.JPG" alt="Photoshop Window Menu" caption="" width="" %}
    </div>
    <div class="col">
{% include figure.html img="PhotoshopActionsWindow.JPG" alt="Photoshop Actions Window" caption="" width="" %}
    </div>
  </div>

- Open one of the Tiff files to be processed in Photoshop.
- In the Action window, click on the Create new action button. Name the action "Tiff>Jpg"

<div class="container">
  <div class="row">
    <div class="col">
     {% include figure.html img="PhotoshopActionsCreateNew.jpg" alt="Photoshop Actions Create New" caption="" width="" %}
    </div>
    <div class="col">
     {% include figure.html img="PhotoshopActionsTiffJpgName.JPG" alt="Photoshop Actions Tiff Jpg Name" caption="" width="" %}
    </div>
  </div>

- Select the "Save As…" command under the File menu. Navigate to the "accessjpg" folder for the project. Choose "Jpeg" from the "Save as type:" drop down menu. Click "Save".

{% include figure.html img="PhotoshopActionsSaveAs.JPG" alt="Photoshop Actions Save As" caption="" width="50" %}
{% include figure.html img="PhotoshopActionsTiffJpgSaveAs.JPG" alt="Photoshop Actions Tiff Jpg Save As" caption="" width="50" %}



- Change the "Quality" value to 10 and click OK.

{% include figure.html img="PhotoshopActionsTiffJpgQuality.JPG" alt="Photoshop Actions Tiff Jpg Quality" caption="" width="50%" %}

- Select "Close" from the File menu or use Ctrl+W.

{% include figure.html img="PhotoshopActionsClose.JPG" alt="Photoshop Actions Close" caption="" width="50%" %}

- Stop recording by clicking the Square "Stop playing/recording" icon in the Actions window.

{% include figure.html img="PhotoshopActionsStop.JPG" alt="Photoshop Actions Stop" caption="" width="50%" %}