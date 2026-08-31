---
section: Metadata
nav_order: 3
title: Legacy Metadata
---

Metadata practice within digital libraries and our Library are continuously evolving. 
Existing collections may have a variety of additional fields beyond our standard guidelines. 
These may be custom to the specific collection needs or represent legacy fields that were commonly used in past practice.
This page lists some of those conventions.

## Legacy Fields

### date_is_approximate 

- **legacy only, don't use for new collections.** In current collections this can be better represented using the `archival_date` field.
- This field lets anyone looking at the collection know that the value in "date" is an estimation only.
- Only fill out 'yes' if the value in "date" field is an estimation. If date is accurate, leave blank.
- Example value: `yes`

### relation

- This field indicates if there are any relationships between resources. 
- An example of this would be if a collection contains material from another collection, or appears in another source. The title of the related collection would be the value for this field. The related collection may be physical or digital.
- This is not an often used field, and will usually be populated by the Digital Projects Manager.

### Legacy CONTENTdm fields

Collections that were migrated out of CONTENTdm in 2023 will have several columns created by CONTENTdm. 
They will generally look like:

`date created,date modified,reference url,cdmid,contentdm file name,contentdm file path`

Please retain: 

- "reference url", rename the column to `cdm_url` (This should not be named "reference_url"! It is helpful to retain this incase we need to look up old CDM urls)
- "cdmid"

The other columns can be removed--if they are retained, rename with "cdm" in front (removing spaces) and do NOT include in data outputs.
