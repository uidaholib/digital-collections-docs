---
section: Maintainers
nav_order: 3
title: Config Search
---

Digital collection data is added to the search index using a standardized JSON form prepped for ingest.
The JSON file is built and deployed with each CollectionBuilder digital collection using a template in "assets/data/search.json"
The mapping between the collection metadata and the "search.json" output is configured in "_data/config-search-index.csv".

Ensuring the mappings in "config-search-index" are correct is essential to having good data for search and aggregation in DPLA.

## Concept

The contents for each item record in "search.json" are modeled on the standard [DCMI core terms](https://www.dublincore.org/specifications/dublin-core/dcmi-terms/) to provide standardized, interoperable data for the search index.
This enables useable search facets and reuse in other platforms.

The "search.json" file is built with each digital collection and exposed on the web. 
The search index application harvests the json to ingest new items or update existing records.
The list of collection json files is used to manage the "Sources" for the search index. 

The list of deployed example "search.json" files is at: 
https://www.lib.uidaho.edu/digital/data/search-links.txt

## search.json 

The "search.json" file has two main keys, "collection" and "items".

- "collection" - contains summary information about the digital collection.
- "items" - contains individual records for each item in the digital collection. 

Custom metadata in each digital collection is mapped to these core fields:
title, date, creator, description, subject, coverage, identifier, source, type, format, language, rights, relation, publisher, genre.

Additionally, in each item record "search.json" provides:

- thumb - full URL to thumbnail image if available.
- transcript - plain text transcript if available.
- file - full URL to item download if available.
- text - `true` if item file is pdf where full text should be extracted by the index. 
- collectionid - unique id for the individual digital collection, based on the collection's url slug (baseurl).
- objectid - unique id for the item within the collection.
- url - direct URL to the item's page.

### Configure 

The contents of the json are configured using the file "_data/config-search-index.csv".
**Do not edit the first column** of the config-search-index, it must contain the same set of dublin core fields for every collection. 
The second column "field" should be customized if necessary to match the most relevant column names in the collection metadata, to enable proper mapping of the metadata to the search index.

In cases where the collection metadata is customized beyond the standard template and contains unique fields, be thoughtful about which fields should be mapped to provide valuable search to users.
If necessary, do metadata work such as combining or cleaning columns to create the most relevant and useful data.

#### genre

One special field for search is "genre" as it will displayed at the top of the search listing. 
By default "genre" is mapped to "display_template" which should work for the majority of collections. 
If the collection has odd customized item layouts that won't make sense as a label in that context, do some metadata work to create a new "genre" column that makes sense, then change the mapping in the config.

#### Full Text search

By default, "search.json" is set to indicate that all items with "format" value of "application/pdf" should be tagged to have their text extracted and entered in full text search.
If this *should not* be the default for a particular collection, comment out `pdf-full-text: true` in the front matter of the "search.json" file.
Individual items can be tagged for full-text by adding a column named "full-text" to the metadata, and giving it value `true`.

#### Default Config

first column of the config should not be modified.

```
dcterm,field
title,title
date,date
creator,creator
description,description
subject,subject
coverage,location
identifier,identifier
source,source
type,type
format,format
language,language
rights,rightsstatement
relation,findingaid
publisher,publisher
genre,display_template
```
