# Pictorial Map Metadata Guidelines: *Requirements and Recommendations for Preparing Metadata for Pictorial Maps Omeka S Site*
Created by Alyssa Sklar, December 2023 for SI 676: Networked Services for Libraries, Archives, and Museums
## Overview
---
## Extracting
---
## Transforming
### Metadata Application Profile (MAP)

This guideline is meant to assist in the expression of all the types of items and the descriptive
information regarding pictorial maps created from 1900-1990 held at the Library of Congress
Geography and Map Division. This information comes from an already existing extant schemas
to be translated into Dublin Core metadata for the purpose of curating an Omeka S site. This is
a model and guide on how to map and model metadata from Library of Congress to the Omeka
S site. The following information includes the referenced namespaces, standards, and
controlled vocabularies that were utilized in the process of metadata crosswalking. As well as a
key to identify which types of information are used, their granularity, and the relationship to the
items in the Omeka S collection.

### Namespaces, Standards, & Controlled Vocabularies Referenced

DCMI Terms: https://www.dublincore.org/specifications/dublin-core/dcmi-terms/

ISO 639-3: https://iso639-3.sil.org/code_tables/639/data

ISO 8601: https://www.iso.org/iso-8601-date-and-time-format.html

LC Genre/Form Terms (LCGFT): https://www.loc.gov/aba/publications/FreeLCGFT/freelcgft.html

Library of Congress Subject Headings (LCSH): https://id.loc.gov/authorities/subjects.html

Getty Thesaurus of Geographic Names (TGN): https://www.getty.edu/vow/TGNSearchPage.jsp

### Metadata Fields Cheatsheet

| LOC Label  | Omeka Label | Status  | DC Term |
| -----------| -----------| ---------| ------ |
|    title   |   Title    | Required | dcterms:title |
|    notes   | Description | Recommended | dcterms:description |
|    format  | Type | Recommended | dcterms:type |
|   medium   | Extent | Optional | dcterms:extent |
|    date    | Date | Recommended | dcterms:date |
| digital_id | Identifier | Optional | dcterms:identifier |
| created_published  | Publisher | Recommended | dcterms:publisher |
| language  | Language | Optional | dcterms:language |
| location | Location | Recommended |dcterms:coverage |
|  subject  | Subject | Recommended | dcterms:subject |
---
## Loading

###
