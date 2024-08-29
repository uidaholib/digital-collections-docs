---
section: Transcription
nav_order: 3
title: Tagging
---

You will be developing a new transcription process for the CDIL. Normally, transcribers would add all of the tags manually beside the text where they think it is most appropriate. 

While this is still an element of the final process, we have implemented a few tools that will hopefully do the majority of the heavy lifting so tags are more accurate, more thorough and implements a *controlled vocabulary*, or an organized arrangement of words and phrases which is necessary for data to be machine readable.

## Text Mining

Tags are generated from a text mining tool made in-house by the Digital Scholarship and Open Strategies department, which searches across all transcripts in a given oral history collection for words relating to specific categories, such as *“factory”*, *“shift”*, *“union”* for **labor** and *"white-collar"*, *"joblessness"*, *"layoff"* for **economics**

{% include figure.html img="transcription_guide_images01.png" alt="Screen capture of Visual Studio Code and code" caption="A snippet of code from the text mining tool seen in Visual Studio Code showing the terms for labor and education" %}

Once these tags and their example words are tallied, this data is pasted into the `Tags` tab of your `Names Locations Tags` spreadsheet located in each of the `Copy Edited` folders.

Using the Google Sheets `Apps Script` extension, you will then deploy a code which will search your transcription for the example words, and autofill your tags column with the associated tag.

**The advantage of using this technique** is that we can:

- Add or remove tags in the Names Locations Tags spreadsheet as needed and the same changes will apply to all of the transcriptions we are working on in that collection
- As a transcriber, you can create entirely new tags and their associated words
- All of the tags will have consistent spelling and data should be more detailed