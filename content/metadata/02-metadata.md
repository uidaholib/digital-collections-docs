---
section: Metadata
nav_order: 2
title: Metadata Guidelines
---

The sections below describe the standard fields and conventions used in our metadata template. 
Additional fields can be added as needed to describe the unique qualities of the collection, however, the standardized fields should be filled as much as possible to ensure interoperability. 

General notes:

- All field names should be lowercase and contain no spaces! (underscore `_` is okay)
- Field values should be plain text only in most cases (i.e. no Markdown or HTML) unless it is a highly customized collection.
- The first column should be objectid, and should be filled for *every* row (i.e. do not have blank values in the first column).
- Ensure you handle CSVs correctly (i.e. do not use Excel to open or create CSVs!). Use Sheets or OpenRefine to correctly transform metadata in CSVs into XLSX or XLSX to CSV.
- If you need a fresh starting spreadsheet, check the blank [metadata template in Sheets](https://docs.google.com/spreadsheets/d/1dRgG-Xd28gRZ9ErbU6-1YtgNM6gHFEh3IFNOwKzpoRc/copy?usp=sharing)

---


### title 
- *required*
- The name of an item. This is either the given title of an item or a short, descriptive set of words to identify the item.  
- All words after the first word in the title should be lower case unless referring to a proper noun such as a name or place (Dylan Fuller, Empire State Building, Idaho, etc.)
- For questions on how to title photographs in a series, please refer to CDIL staff.
- Example values: `Hecla Mine`; `Students playing baseball`

### description
- *required* 
- A detailed, 1-3 sentence accounting of the item, communicating what it is and its contents.
- This includes small details such as "mountains can be seen in the background", and should include names when known. 
- All descriptions should be in complete sentences, with a single space between sentences. Descriptions should be no more than 1-3 sentences.
- Example value: `Students on lawn in front of old Gault Hall, which was torn down in 2003 to make room for the current Living Learning Center.`

### subject
- *required* 
- Words or phrases that describe or relate to the material. Think of how you would search for the item. What key words would you use to find what is described/depicted in the item? 
- Subjects allow researchers and people interested in searching for one thing in particular to narrow the collections down to their interests. 
- Use the [Getty Art and Architecture Thesaurus](http://www.getty.edu/research/tools/vocabularies/aat/) to locate subject terms. 
- Multiple entries (2-4) are encouraged when possible, and should be separated with a semi-colon and a single space. 
- Some collections have a controlled vocabulary related to the subject material, so be sure to check with a supervisor before you start assigning subjects.
- Example values: `children; parades; automobiles`; `cows (mammals); farming (function)`

### creator
- The individual or entity that created the item. 
- For articles or publications, this is the author. 
- For photographs, either the photographer or the studio. 
- Use format: Last name, First name
    - If additional names are included, use this order: Last name, First name "Nickname" Middle name Maiden name.
- Example values: `Riegger, Hal`; `Barnard Studio (Wallace, Idaho)`

### date  
- Refers to the date the item was created/published in ISO format yyyy-mm-dd. 
- If you know the exact date for an item, fill it in using the yyyy-mm-dd format.
- If you only know the year and month, simply leave off the day: 1955-12. Likewise, if you only know the year, just enter the year: 1955. 
- If there is no year included with the item, you can estimate the date to the nearest decade if you know enough information about the content of the image or item. 
    - For example, if you think a photo was probably taken in the 1950s based on a car or clothing pictured, you can put '1950' or '1955' in the data cell. Be sure to fill in the date range in YYYY-YYYY format (in this case, 1950-1960) in the 'archival_date' cell in this situation, but do not put the range in the "date" column.
- If you do not know the date and cannot estimate it, simply leave this field blank.
- Example values: `1955-12-08`; `1955-12`; `1955`

### archival_date
- This is an alternate, non-ISO date field to represent the ambiguity of some object dates.
- If an object's date is somewhere within an approximate date range (i.e. "2020-2030" or "2020-2025"), enter that range into this cell in the format YYYY-YYYY.
- In the event that no date is known, enter the value `undated`.
- For all other dates, the Digital Projects Manager will populate the values in the format DD Month YYYY, Month YYYY, or YYYY.
- Example values: `26 October 2023`; `October 2023`; `2023`; `2020-2030`; `undated`

{% capture archival-date %}
#### Staff instructions to populate archival date

- Use this formula to populate the archival date field in Google Sheets using the "date" field in the format YYYY-MM-DD. `=TEXT(cell,"dd")&" "&TEXT(cell,"mmmm")&" "&TEXT(cell, "yyyy")`
- In the formula above, you will need to replace "cell" with the cell reference containing the date. For example: `A2`
- For dates without a day (YYYY-MM), use the following formula.
`=TEXT(cell,"mmmm")&" "&TEXT(cell, "yyyy")`
{% endcapture %}

{% include alert.html text=archival-date color="info" %}

### date_is_approximate 
- **legacy only, don't use for new collections**
- This field lets anyone looking at the collection know that we are certain of our estimation, not that our estimation is the accurate date.
- Only fill out 'yes' if the Year, Year-Month, or an actual estimation is provided. If date is accurate, leave blank.
- Example value: `yes`

### location
- The geographic location(s) / place names to which the item is tied. 
- 'City, State' format, but can sometimes extend to 'City, County, State, Country' depending on the collection (check with a supervisor to be sure). 
- Separate multiple location entries for a single record with a semicolon (;).
- Example values: `Boise, Idaho`; `Potlatch, Latah County, Idaho`; `Jakarta, Indonesia`

### latitude 
- A geographic coordinate specifying the north-south position of an item.
- Latitude and longitude can be found using [Google Maps](www.maps.google.com) or [iTouchMap](itouchmap.com/latlong.html). 
    - On [Google Maps](www.maps.google.com), search for the approximate location then right click on a point. Select the lat/long displayed at the top of the menu. This will copy the values to your clipboard.
    - On [iTouchMap](itouchmap.com/latlong.html), search or move the map to approximate location, then hold Shift and click on the spot. The lat/long will display below.
- Copy and paste the coordinates from either of these sites into the field in the metadata sheet. 
- The lat/long values will need to be split into the two fields. 
- Example value: `46.731634`

### longitude
- A geographic coordinate specifying the east-west position of an item. Follow "latitude" instructions above to locate longitude data.
- Example value: `-117.165625`

### identifier
- The unique identifier assigned to the object by the object's (usually physical) source collection in Special Collections.
- This is usually found on the folder or box the object is in. 
- For new collections the identifier should always match the object's filename. See the [filenaming docs]({{ '/content/scanning/02-filenaming.html' | relative_url }}) for more information.
- Example value: `ARG-1993-02-16`

### format_original
- This field specifies the format of the physical object that was digitized. 
- There is no controlled vocabulary for this field. Choose a word or phrase that best describes the format, and try to be consistent across items in a single collection.
- Example values: `black-and-white photograph, color photograph, article, scrapbook, newspaper clipping, magazine`  

### format
- *required* 
- The digital format of the item. 
- This field lets the viewer know what format the uploaded material is.
- Choose from one of the following options: 
    - Image: `image/jpeg`
    - Document: `application/pdf`
    - Audio: `audio/mp3`
    - Video: `video/mp4`

### filename
- *required* 
- Identifier PLUS extension (.jpg, .tif, .pdf, .wav, etc.) 
- The value must exactly match the actual filename, including capitalization. This value is case-sensitive!
- Our digital content management system uses this field to correctly link the digitized item to the corresponding metadata entry. 
- When possible, a pre-set formula will add the correct extension to each identifier entered in previous columns to save from any re-entry errors. 
- The filename values will be generated by staff in most cases. 
- See the [filenaming docs]({{ '/content/scanning/02-filenaming.html' | relative_url }}) for more information.
- Example value: `ua2011-30_1913-14.pdf`

### source
- The physical source of the material being scanned. 
- Sometimes this is a single physical collection here at U of I and sometimes this is from several collections (check with your supervisor to identify the source of the items you are describing). 
- This will sometimes include the physical collection's collection number or call number, so people are able to find the item in-person if they want to.
- Generally follows the pattern "collection name, collection number (if available), organization name, link".
- Example value: `Idaho Cities and Towns Photographs, PG 5, University of Idaho Library Special Collections and Archives`

### type
- This field indicates what type of content the material contains (image, sound, text, etc.) using a one- or two-value input. 
- Choose from the following options: 
    - `Text`: Any typed or written material (even if it's a photograph of textual material).
    - `Image;StillImage`: Photographs, negatives, etc.
    - `Image;MovingImage`: Video
    - `Sound`: Audio recording
    - `Collection`: Compound object
    - `Image;PhysicalObject` or `Text;PhysicalObject`: 3D object
    - `Dataset`: Dataset
    - `InteractiveResource`: Webpage, VR environment
    - `Software`: Computer program
- You may only choose one value for the type field. If you encounter an item with multiple types of content, choose the option that describes the item best.
- At minimum, the input should contain a value chosen from the [DCMI Type Vocabulary](https://www.dublincore.org/specifications/dublin-core/dcmi-type-vocabulary/2003-02-12/).
- Example values: `Image;StillImage`; `Image;MovingImage`; `Text`; `Sound`

### finding_aid
- A link to the finding aid for the physical version of this resource, if it exists.
- The value should be simply a URL without any HTML markup.
- Example value: `https://archiveswest.orbiscascade.org/ark:/80444/xv40698/`

### relation
- This field indicates if there are any relationships between resources. 
- An example of this would be if a collection contains material from another collection, or is similar to material in another collection. The title of the related collection would be the value for this field. The related collection may be physical or digital.
- This is not an often used field, and will usually be populated by the Digital Projects Manager. 
- Example values: [The Argonaut](https://www.lib.uidaho.edu/digital/argonaut/) digital collection might include the `Argonaut Photograph Collection` as a relation

### digital_collection
- This field contains the name of the digital collection to which all of the material you are working with belongs. 
- It lets those viewing the item know where they can find more materials related to this item in case they found it by searching for a subject, or through another linked entry. 
- This also provides a connection with the physical material and helps individuals to know where it is located. 
- Example value: `Argonaut Photograph Collection`

### contributing_institution
- Most of our digital collections are owned by the University of Idaho Library, but some of them originate from other institutions or individuals. Some digital collections are combinations of U of I Library materials and materials from other institutions. 
- When appropriate, citing the Contributing Institution notes attribution as well as protects U of I from potential copyright issues. 
- Example value: `Potlatch Historical Society`

### language
- A three-letter code for the language used in the material. 
- Use the [ISO 639-2 Codes for the Representation of Names and Languages](https://www.loc.gov/standards/iso639-2/php/code_list.php) to identify the correct language code.
- Multiple language codes should be separated by a semi-colon.
- Example value: `eng`, `fre`, `spa`

### rights
- A copyright statement that consists of a free-text statement and a standardized rights statement. 
- These statements indicate to viewers and researchers if permissions are required to use the material in publication, and how to attribute the item once used. 
- Suggested value for material **in copyright**: `In copyright, educational use permitted. Educational use includes non-commercial reproduction of text and images in materials for teaching and research purposes. For other contexts beyond fair use, including digital reproduction, please contact the University of Idaho Library Special Collections and Archives Department at libspec@uidaho.edu. The University of Idaho Library is not liable for any violations of the law by users.`
- Suggested value for **no copyright**: `Material has likely passed into public domain. Digital reproductions are made available by University of Idaho Library for educational purposes, and future use should acknowledge this repository. For more information, please contact University of Idaho Library Special Collections and Archives Department at libspec@uidaho.edu. The University of Idaho Library is not liable for any violations of the law by users.`
- Not sure about the rights for your item? Refer to the [Cornell Library copyright guide](https://guides.library.cornell.edu/copyright/publicdomain) to determine if the item is old enough that its copyright has expired.

### rightsstatement
- This field is a standardized rights statement, designated in the form of a URI (Uniform Resource Identifier). 
- It should be presented as a [creativecommons.org](https://creativecommons.org/) URI or a [rightsstatements.org](https://rightsstatements.org/en/) URI. 
- Options include:
    - **In Copyright - Educational Use Permitted**: `http://rightsstatements.org/vocab/InC-EDU/1.0/`
    - **No Copyright**: `http://rightsstatements.org/vocab/NoC-US/1.0/`
- In most cases, you'll use the URI for "Educational Use Permitted". Only use the URI value (starts with `http`), *not* the words "Educational Use Permitted".
- For additional options not shown above, see [rightsstatements.org](https://rightsstatements.org/en/).
- Example value: `http://rightsstatements.org/vocab/NoC-US/1.0/`

### filename_original
- Refers the original filename (typically of a born digital transferred file) that may have been edited to fit our standards here at the Library or has been renamed to match collection conventions. This can be useful for future work tracking issues or debugging problems. 

------------

## Legacy CONTENTdm fields

Collections that were migrated out of CONTENTdm in 2023 will have several columns created by CONTENTdm. 
They will generally look like:

`date created,date modified,reference url,cdmid,contentdm file name,contentdm file path`

Please retain: 

- "reference url", rename the column to `cdm_url` (This should not be named "reference_url"! It is helpful to retain this incase we need to look up old CDM urls)
- "cdmid"

The other columns can be removed--if they are retained, rename with "cdm" in front (removing spaces) and do NOT include in data outputs.
