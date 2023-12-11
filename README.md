# Pictorial Map Metadata Guidelines: *Requirements and Recommendations for Preparing Metadata to Load into Omeka S*
Created by Alyssa Sklar, December 2023 for SI 676: Networked Services for Libraries, Archives, and Museums

## Overview

The following guidelines and processes extracts information from the Library of Congress Geography and Map Division items related to pictorial maps in order to transform the metadata and load into an Omeka S site. The Omeka S site is found at: https://amsklar.projectst.si.umich.edu/omekas/omeka-s/s/pictorial-maps/page/pictorial-maps-about

### Structure of Repository

- `MAP.ipynb`: contains the script to extract, tranform, and begin the process of uploading the item set and their respective items to an Omeka S site relating to pictorial maps.
- `pictorial`: contains the outputs of `MAP.ipynb` such as .json files that were extracted from the Library of Congress, CSV files, and more.

To demonstrate the extract, transform, and load process on an additional collection, an Omeka S site of transit maps from the Library of Congress was created. This information can be found in `transit`.

Lastly, `LOC_libraries` contains a slightly different extract, load, and transform process from the pictorial and transit collections and details listed below. But, it served as an introduction and first attempt at this process. This collection is from the Free to Use and Reuse Libraries collection at the Library of Congress.

---
## Extracting

Information regarding pictorial maps created from 1900-1990 held at the Library of Congress Geography and Map Division was extracting by using an endpoint to search for items by map format, with subject of pictorial maps, and returns up to 150 results.

Collection level metadata was extracted to compile item Title, Image URL, and the URL of the item. Results can be found in `pictorial_collection.csv `

Item level metadata was extracted to .json format. To which the results were compiled into a CSV.  Results can be found in `pictorial_metadata.csv`

---
## Transforming
### Metadata Application Profile (MAP)

This guideline is meant to assist in the expression of all the types of items and the descriptive
information. This information comes from an already existing extant schemas
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

### Guidelines Key
| <!-- -->    | <!-- -->   | 
| -------- | ----- |
| **LOC Label** | Field label used by Library of Congress |
| **Omeka Label** | Field label used in Omeka S |
| **Status** |  Identifies if a field is required, recommended, or optional |
| **Description** | Description of the field |
| **DC Term** | The qualified Dublin Core element to which a field should map |
| **Repeatable** | Identifies if a field is repeatable |
| **Notes and Best Practices** | Includes recommendations for a field’s content and application |

### Fields
| <!-- -->    | <!-- -->   | 
| -------- | ----- |
| **LOC Label** | title |
| **Omeka Label** | Title |
| **Status** | Required |
| **Description** | Name given to the resource |
| **DC Term** | dcterms:title |
| **Repeatable** | No |
| **Notes and Best Practices** | • Can include explanatory or qualifying symbols (e.g. brackets) • If a formal title does not exist do not use “Unknown” • Example: Paul Sample's America, its soil |

| <!-- -->    | <!-- -->   | 
| -------- | ----- |
| **LOC Label** | notes  |
| **Omeka Label** | Description  |
| **Status** | Recommended |
| **Description** | Description of the resource to capture the “aboutness” |
| **DC Term** | dcterms:description|
| **Repeatable** | Yes |
| **Notes and Best Practices** | • Description at object-level is preferred, but can include collection description if applicable • Example: Series of 10 pictorial wall maps issued as posters to illustrate the military successes of the Red Army in the Russian Civil War of 1917-1922.|

| <!-- -->    | <!-- -->   | 
| -------- | ----- |
| **LOC Label** | format  |
| **Omeka Label** | Type  |
| **Status** | Recommended |
| **Description** | Physical medium of the resource |
| **DC Term** | dcterms:type |
| **Repeatable** | Yes |
| **Notes and Best Practices** | • Use standard vocabularies such as LC Genre/Form Terms (LCGFT) • Example: cartographic • Example: map |

| <!-- -->    | <!-- -->   | 
| -------- | ----- |
| **LOC Label** | medium  |
| **Omeka Label** | Extent |
| **Status** | Optional |
| **Description** | The size of resource including number of pages, length, width, height|
| **DC Term** | dcterms:extent |
| **Repeatable** | Yes |
| **Notes and Best Practices** | • For dimension, include abbreviation of units • Use a semicolon to separate multiple values • Example: 1 map ; 35 x 56 cm, folded to 21 x 31 cm|

| <!-- -->    | <!-- -->   | 
| -------- | ----- |
| **LOC Label** |  date |
| **Omeka Label** | Date |
| **Status** | Recommended |
| **Description** | Date of creation |
| **DC Term** | dcterms:date |
| **Repeatable** | Yes |
| **Notes and Best Practices** | • Do not use placeholder values such as “Unknown” • Should follow ISO 8601 format: (YYYY-MM-DD) • Example: 1946-01-01|

| <!-- -->    | <!-- -->   | 
| -------- | ----- |
| **LOC Label** | digital_id |
| **Omeka Label** | Identifier |
| **Status** |  Optional |
| **Description** | A unique value to reference the digital resource within the institution’s collection |
| **DC Term** |dcterms:identifier   |
| **Repeatable** | No |
| **Notes and Best Practices** | Recommended alphanumeric string that can include special characters |

| <!-- -->    | <!-- -->   | 
| -------- | ----- |
| **LOC Label** | created_published   |
| **Omeka Label** | Publisher  |
| **Status** | Recommended  |
| **Description** | An entity responsible for making the resource available, can include person, an organization, or service along with location and date |
| **DC Term** | dcterms:publisher |
| **Repeatable** | Yes |
| **Notes and Best Practices** | • If location and entity are present, use colon to separate • Not to be used for the entity that makes the material available • Example: New York : Associated American Artists |

| <!-- -->    | <!-- -->   | 
| -------- | ----- |
| **LOC Label** | language  |
| **Omeka Label** | Language |
| **Status** | Optional  |
| **Description** | Language expressed in resource that contains text |
| **DC Term** | dcterms:language |
| **Repeatable** | Yes |
| **Notes and Best Practices** | • Use standard vocabulary ISO 639-3 • Example: eng • Example: rus |

| <!-- -->    | <!-- -->   | 
| -------- | ----- |
| **LOC Label** | location  |
| **Omeka Label** | Location  |
| **Status** | Recommended |
| **Description** | The spatial or temporal topic of the resource |
| **DC Term** | dcterms:coverage |
| **Repeatable** | Yes |
| **Notes and Best Practices** | • Use standard vocabulary TGN when possible • Example: New York (State)--New York • Example: Harlem (New York, N.Y.) •Example: home of franklin d. roosevelt national historic site |

| <!-- -->    | <!-- -->   | 
| -------- | ----- |
| **LOC Label** | subject  |
| **Omeka Label** | Subject |
| **Status** |  Recommended |
| **Description** | The topic of the resource |
| **DC Term** |dcterms:subject |
| **Repeatable** | Yes |
| **Notes and Best Practices** | • Use standard vocabulary LCSH when possible • Can include geographic or forms, include -- to separate values • Example: Natural resources--United States--Maps • Example: Central business districts |

### Scripting

The item level metadata located in `pictorial_metadata.csv` was transformed based on the interested field outlined above and headers were re-named. See `pictorial_metadata_transform.csv` for results. Next, item level information was extracted from list format and the deliminator was chagned from `,` to `/` for more streamlined loading into Omeka S. 

Additionally, since `pictorial_metadata_transform.csv` contains all results of pictorial maps betwen 1900 and 1990, the file was subsetting based on Subjects China, Japan, and United States. Resulting in `pictorial_metadata_China.csv`, `pictorial_metadata_Japan.csv`, and `pictorial_metadata_US.csv`.

---
## Loading

A site to host the items and their metadata was created in Omeka S entitled Pictorial Maps.

Next, three item sets were created in `MAP.ipynb` to hold the items related to Japan, China, and the United States. 

Using the CSV Import Module (version 2.5.0) in Omeka S by Omeka Team and Daniel Berthereau, items for their respective item sets were loaded to Omeka using the tranformation guidelines listed above. Additional guidelines are as follows:

| Column | Mappings | Options |
| -------- | ----- | ----- |
|Type|   Type| Multivalue |
| Extent |  Extent | Multivalue |
| Date |  Date | |
| Image_URL| Media source[URL]  | |
| Description |  Description | Multivalue |
| Identifier |  Identifier | |
| Creator |  Creator | Multivalue |
| Publisher | Publisher  | Multivalue |
| Language |  Language | Multivalue |
| Location |  Coverage | Multivalue  |
| Subject |  Subject | Multivalue  |
| Title |  Title |  |

Importantly, the multivalue deliminator is a `/`. This was specified in the transformation process script. 

---
## Results

The final Omeka S site of pictorial maps contains four pages: About, Japan, US, and China. It also features a View All section to allow users to view all the maps in one place regardless of their location affilation of Japan, China, or United States. View the Pictorial Maps site: https://amsklar.projectst.si.umich.edu/omekas/omeka-s/s/pictorial-maps/page/pictorial-maps-about

Additionally, a site showcasing Transit Maps was created to demonstrate the extract, transform, and load process from pictorial maps could be replicated: https://amsklar.projectst.si.umich.edu/omekas/omeka-s/s/transit-maps/page/about

And another site was created in the testing and implemention phase related to the Free to Use and Reuse Library of Conress Collection of Libraries. This site can be found here: https://amsklar.projectst.si.umich.edu/omekas/omeka-s/s/loc-libraries/page/welcome

