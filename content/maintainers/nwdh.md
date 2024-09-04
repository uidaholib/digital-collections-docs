---
section: Maintainers
nav_order: 2
title: NWDH Harvest
---

[North West Digital Heritage](https://www.northwestdigitalheritage.org/) (NWDH) harvests our metadata via an XML file that aggregates all collections.
NWDH then contributes our records to DPLA ([view U of I items](https://dp.la/search?partner=%22Northwest+Digital+Heritage%22&provider=%22University+of+Idaho%22&page=1) or all [NWDH DPLA](https://nwdh.dp.la/)).

The process for generating the XML file is set up in [metadata-harvest](https://github.com/uidaholib/metadata-harvest).
It should be regenerated and redeployed when new collections are added or significant changes have been made. 

## Required Metadata

The NWDH XML harvest file is built on the search.json conventions used for our centralized search. 
So work on debugging issues in the XML metadata will be in the mapping used for search.json.
It is important to note the required fields for NWDH aggregation which informs our metadata practices.

### Mandatory for each item

- Title
- Link (permanent link to item/record in source repository) - item url
- Provider (Holding institution; we can also just default to ‘University of Idaho’ for everything) - `University of Idaho`
- Rights URI (from RightsStatements.org or Creative Commons) - item "rightsstatement", default `http://rightsstatements.org/vocab/UND/1.0/`
- Type (from DCMI vocabulary (aka ‘Text’, ‘Image’, ‘Sound’, etc.) - item type, otherwise reasons based on search.json "genre".

### Optional, but preferred

- Identifier (A unique identifier for the item in your system) - objectid
- Thumbnail (A link to either a full, or thumbnail, version of the item, for example, ending in ‘.jpg’) - image_thumb

### Optional

- Creator
- Date
- Description
- Freetext (this is if you want to include an additional free text rights & use statement, i.e., in addition to the required rights uri)
- Full (only used if you want to send public domain content to Wikimedia Commons)
- IntermediateProvider (typically used when an institution is hosting another’s institution’s digital collections)
- Language
- Medium (the document genre, i.e., ‘black and white photographs’, ‘pamphlets’, ‘postcards’, etc.)
- Publisher (i.e., of the original object)
- Relation (Collection name, although if you were to keep that that in your xml file, as you provide in the json file you shared, we would just get it from there)
- Spatial (aka Coverage. Location or place name)
- Subject
- TitleAlternative
