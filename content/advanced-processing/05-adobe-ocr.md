---
section: Advanced Processing
nav_order: 5
title: Optical Character Recognition
---

After a PDF is created, the CDIL usually runs an Optical Character Recognition(OCR) process on the file using Adobe Acrobat. This OCR process can make the document text searchable by users and usually reduces the file size of the document. More recent versions of Adobe Acrobat have improved the algorithm used in the OCR process, so it is best to use the most recent version of the Acrobat software that is available. Cursive text and unusual typeface may not be converted to searchable text.

## Optical Character Recognition (OCR) in Adobe Acrobat Pro DC

- Adobe Acrobat Pro DC has the OCR functions accessed from different menus.

- With a PDF document open, select the "Scan & OCR" tool from the available tools on the right side of the application window.

{% include figure.html img="AdobeProDCSidebar.jpg" alt="Adobe ProDC sidebar" width="25%" %}

- Select the "Recognize Text" option on the Toolbar and select "In This File" from the dropdown menu.

{% include figure.html img="AdobeProDCScanOCRToolbar.jpg" alt="Adobe ProDC Scan OCR Toolbar" width="100%" %}

- Make sure the Settings are correct. PDFs should be downsampled to 300 dpi to reduce file size issues.

{% include figure.html img="AdobeProDCOCRSettings.JPG" alt="Adobe ProDC ORC Settings" width="75%" %}

- Click on the "Recognize Text" button to begin the process. Once the process has finished, save and close the file.

{:#photoshop-batch-actions}
## Acrobat Batch OCR

- In Adobe Acrobat Pro DC select the Tools window.

{% include figure.html img="AdobeProDCToolsWindow.JPG" alt="Adobe ProDC Tools Window" width="50%" %}

- Click on the "Scan & OCR" icon in the "Create & Edit" tool group.

- Click on the "Or recognize text in multiple files" option underneath the blue "Start" button.

{% include figure.html img="AdobeProDCScanOCRTool.JPG" alt="Adobe ProDC Tools Window" width="50%" %}

- Add all the files to be reduced either with the "Add Files…" button or by drag and dropping files to the window.

{% include figure.html img="AdobeProDCBatchOCRFiles.JPG" alt="Adobe ProDC Batch OCR Files" width="75%" %}

- Choose to save the files to the same folder as the originals or to save all the files to a new folder. Then choose to either use the same file names and overwrite the existing files or add a text string either before or after the original file name. Click OK.

{% include figure.html img="AdobeProDCBatchReduceOutput.JPG" alt="Adobe ProDC Batch Reduce Output" width="%75" %}

- Check the General Settings dialog that opens. PDFs should be downsampled to 300 dpi to reduce file size issues. Click OK to start the process.
