---
section: Transcription
nav_order: 4
title: Code
---

When you open the spreadsheet with your transcript, you are going to go to the `Extensions` tab and then open `Apps Script`, which will pop out in its own window. Select all of the sample code in the terminal and replace with the following (`updated 07/09/2024`):


```

function fillTags() {
  // Get the active spreadsheet
  var spreadsheet = SpreadsheetApp.getActiveSpreadsheet();
  
  // Get the transcript sheet by name
  var transcriptSheet = spreadsheet.getSheetByName("rwhp088");
  if (!transcriptSheet) {
    Logger.log("Transcript sheet not found");
    return;
  }
  
  // Set the header in cell E1 to "tags"
  transcriptSheet.getRange("E1").setValue("tags");
  
  // Get the tags spreadsheet by URL
  var tagsSpreadsheet = SpreadsheetApp.openByUrl("https://docs.google.com/spreadsheets/d/1LywmnJ2NFkmdjBiihhRrURo2xJMcANQM770YfKvlqL8/edit?gid=244961975#gid=244961975");
  if (!tagsSpreadsheet) {
    Logger.log("Tags spreadsheet not found");
    return;
  }
  
  // Get the tags sheet within the tags spreadsheet
  var tagsSheet = tagsSpreadsheet.getSheetByName("tags");
  if (!tagsSheet) {
    Logger.log("Tags sheet not found");
    return;
  }
  
  // Get the range of the transcript column
  var transcriptRange = transcriptSheet.getRange("D2:D" + transcriptSheet.getLastRow());
  var transcriptValues = transcriptRange.getValues();
  
  // Get the range of example words and tags in the tags sheet
  var exampleWordsRange = tagsSheet.getRange("B2:B" + tagsSheet.getLastRow());
  var tagsRange = tagsSheet.getRange("A2:A" + tagsSheet.getLastRow());
  var exampleWordsValues = exampleWordsRange.getValues();
  var tagsValues = tagsRange.getValues();
  
  // Create a map of example words to tags
  var tagsMap = {};
  for (var i = 0; i < exampleWordsValues.length; i++) {
    var word = exampleWordsValues[i][0].toLowerCase();
    var tag = tagsValues[i][0];
    tagsMap[word] = tag;
  }
  
  // Initialize an array to store the tags for each transcript entry
  var transcriptTags = [];
  
  // Loop through each transcript entry
  for (var i = 0; i < transcriptValues.length; i++) {
    var text = transcriptValues[i][0];
    var uniqueTags = [];
    
    if (typeof text === 'string') {
      // Use regular expression to extract words and handle punctuation
      var words = text.match(/\b\w+['-]?\w*|\w+['-]?\w*\b/g);
      
      // Check each word in the transcript entry against the tags map
      if (words) {
        for (var j = 0; j < words.length; j++) {
          var word = words[j].toLowerCase().replace(/[.,!?;:()]/g, '');
          var singularWord = word.endsWith('s') ? word.slice(0, -1) : word;
          
          if (tagsMap.hasOwnProperty(word) && !uniqueTags.includes(tagsMap[word])) {
            uniqueTags.push(tagsMap[word]);
          } else if (tagsMap.hasOwnProperty(singularWord) && !uniqueTags.includes(tagsMap[singularWord])) {
            uniqueTags.push(tagsMap[singularWord]);
          }
        }
      }
    }
    
    // Add the determined tags to the array
    transcriptTags.push([uniqueTags.join(";")]);
  }
  
  // Get the range of the tags column in the transcript sheet, starting from E2
  var tagsColumn = transcriptSheet.getRange("E2:E" + (transcriptTags.length + 1));
  
  // Set the values in the tags column to the determined tags
  tagsColumn.setValues(transcriptTags);
}
```

**Now revise two elements within the code**:

- Replace `rwhp070` with the name of the tab of your transcript, so it might read something like `andrew.anderson`
An easy way to do this with little fuss is to right click the tab name, select Rename, and copy the text
- Replace the URL on `line 13` with the URL of the collection’s `Name Location Tags` spreadsheet while you are on the tags tab
- Now select the blue deploy button on the top right 
- Select `New Deployment`
- Select type > `Library` and name the script `“fillTags”`
- Now hit the run icon, which looks like a play button
- Select `Review Permissions`, which will open up a warning
- Select `Advanced`, then select the option on the bottom, which will allow you approve permissions with your Gmail address

Now whenever you make changes to the Name Location Tags spreadsheet, you can Run the script to see those changes reflected in your transcript!

**Note!**
For bilingual transcriptions where the non-English language is in column B and the English translation is in column C, make the following change to `line 34`:

```
var exampleWordsRange = tagsSheet.getRange("C2:C" + tagsSheet.getLastRow());
```