# Geoscience Data Catalogue

The GSQ Data Catalogue is an index of all geoscience-related data in digital, physical, or federated form.

The primary goal of the data catalogue is to make geoscience data FAIR.

## Making Data Findable, Accessible, Interoperable, Reusable (FAIR)
<p align="center">
<img src="https://github.com/geological-survey-of-queensland/gsq-info-model/blob/master/wiki-photos/FAIR-Data-image-map-graphic-v2-721px.png" width="721px"><br>
Figure 1: FAIR Data Principles</p>

* **Findable**: Data and supplementary materials have sufficiently rich metadata and a unique and persistent identifier
* **Accessible**: Metadata and data are understandable to humans and machines. Data is deposited in a trusted repository.
* **Interoperable**: Metadata use a formal, accessible, shared, and broadly applicable language for knowledge representation.
* **Reusable**: Data and collections have a clear usage licenses and provide accurate information on provenance.

## Core components of the data catalogue:
1. **Data Portal Catalogue** – a CKAN-based data catalogue with a number of extensions that improve user experience and performance.
1. **Data Store** - low cost, high volume data object storage (AWS S3 buckets).
1. **Data Schemas** - standardised data models that represent a dataset: its metadata, elements and attributes, and relationships to other datasets and data elements. The data schemas based on DCAT2, ISO, GGIC, PPDM, and other standards.
1. **Controlled Vocabularies** – agreed sets of terms to enable data to be shared and reused across application, enterprise, and community boundaries.
1. **Persistent Identifiers (PID)** – a long-lasting reference to a digital resource such as a document, file, web page, or other object.
1. **Linked Data** – connecting related data so that a person or machine can explore the web of data. With linked data, when you have some of it, you can find other, related, data.

## The 3 data catalogues
1. **GSQ Open Data Portal** - a freely available catalogue of geoscience data.
1. **GSQ Internal Data Portal** - an internal catalogue of data that is not yet classified as open data.
1. **GSQ Knowledgebase** - a data catalogue of GSQ-owned datasets for use by GSQ geoscientists and other departmental users. NOTE: The Knowledgebase and Internal Data Portals are the same CKAN instance.

## Work required by the supplier to develop the Data Catalogue:
### Data Catalogue:  
1. Extend and optimise the CKAN Data Catalogue technology platform to enhance functionality, performance, and usability.  
1. Programmatically populate the data catalogue from existing metadata systems MERLIN, QDEX Reports, QDEX Data, GEM, geochemistry Microsoft Access database.  
1. Programmatically populate the data catalogue with metadata for geoscience data objects that are not in existing metadata systems, e.g. data on NAS or other storage. This will include activities such as extracting metadata from file header data.  
1. Optimise the search functionality for the data catalogue. CKAN uses SOLR as its search engine, but we are open to additional search capability, particularly that which allows for facetted searching and the ability to search across specific data attributes across the data store.  
1. Configure the security of the data catalogue according to the Access Rights security schema: e.g. open access, embargoed access, restricted access, metadata only access.  

###	Data schemas:  
1. Assist GSQ staff to create, optimise and extend geoscience data schemas.  
1. Create schema validations.  

### Controlled vocabularies  
1. Optimise the performance and functionality of the vocabulary management tools. 
1. Integrate external (non-GSQ) master data sources into the vocabulary manager.  

### Persistent identifiers  
1. Integrate the data catalogue, lodgement forms, and other data collections to existing PID minting services.  
1. Create PID minting services where no National or State minting service is available.  
1. Apply PIDs to legacy data as part of data migration to the data catalogue and data lake.  

### Linked data  
1. Assist GSQ staff in the creation, extension, and optimisation of linked data.  
1. Optimise the performance and end user experience of the graph database to make data more discoverable and interactive.  
1. Implement visualisations of the linked data.  
1. Implement APIs to the graph database.  

## CKAN extensions
The following CKAN extensions are currently installed in the pilot CKAN platforms:

|Plugin|Purpose|Deployed in|URL|
|---|---|---|---|
|ckanext-spatial|Adds geospatial capabilities to CKAN|Open & Private|[URL](https://github.com/geological-survey-of-queensland/ckanext-spatial.git)|
|ckanext-saml2|Enables SAML2 based SSO|Private|[URL](https://github.com/DataShades/ckanext-saml2)|
|ckanext-scheming|Create custom metadata forms|Open|[URL](https://github.com/geological-survey-of-queensland/gsq-ckanext-scheming.git)|
|ckanext-scheming|Create custom metadata forms|Private|[URL](https://github.com/geological-survey-of-queensland/gsq-kb-ckanext-scheming.git)|
|ckanext-theming|Enables SAML SSO|Open|[URL](https://github.com/geological-survey-of-queensland/gsq-ckanext-gsq-theme.git)|
|ckanext-theming|Enables SAML SSO|Private|[URL](https://github.com/geological-survey-of-queensland/gsq-kb-ckanext-gsq-theme.git)|
|ckanext-datapusher|Enables SAML SSO|Open|[URL](https://github.com/ckan/datapusher.git)|
|ckanext-pdfview|Enables SAML SSO|Open & Private|[URL](https://github.com/ckan/ckanext-pdfview.git)|
|ckanext-cloudstorage|Enables storage of resources in AWS S3|Open & Private|[URL](https://github.com/TkTech/ckanext-cloudstorage.git)|
|ckanext-dcat|Provides DCAT2 metadata export|Open & Private|[URL]()|

The following CKAN extensions are to be considered for implementation into the CKAN platforms:


## Data migration into the Data Catalogue
The following data migration is required:

|Source|Dataset|Metadata source|Target data schema|Comments|
|---|---|---|---|---|
|QDEX Data|3D Models|QDEX Data|DCAT2 Dataset|--|
|QDEX Data|Airborne Geophysics|GEM|Airborne Surveys|--|
|QDEX Data|ASTER|QDEX Data|ASTER|--|
|QDEX Data|Geological mapping data|--|DCAT2 Dataset|--|
|QDEX Data|GIS packages|QDEX Data|DCAT2 Dataset|--|
|QDEX Data|--|--|--|--|
|QDEX Data|--|--|--|--|
|QDEX Data|--|--|--|--|
|QDEX Data|Wireline Logs|--|--|--|
|Lodgement Portal|Open Exploration Reports|--|--|--|
|Lodgement Portal|Open Industry Consultative Reports|--|--|--|
|QDEX Reports|Queensland Geological Maps|--|--|Reports|
|QDEX Reports|GSQ Record Series|--|--|Reports|
|QDEX Reports|Soils and Land Resources Reports|--|--|Reports|
|QDEX Reports|GSQ Exploration Reports|--|--|Reports|
|QDEX Reports|Departmental Publications|--|--|--|
|QDEX Reports|GSQ-Commissioned Industry Studies/Reports|--|--|--|
|--|--|--|--|--|
|--|--|--|--|--|
|--|--|--|--|--|
|--|--|--|--|--|
|--|--|--|--|--|
|--|--|--|--|--|
|--|--|--|--|--|
|--|--|--|--|--|
|MERLIN|Bibliographies|MERLIN|DCAT2 Dataset|--|

# CKAN Facets
| Facet | Type  | AND/OR  | Metadata Field  |
|---|---|---|---|
| Spatial bounds | Bounding box | AND | spatial |
| Data Types | Facet | AND | dataset\_type |
| Commodities | Facet/multiple | OR | commodity |
| Earth Science Data Category | Facet | AND | earth\_science\_data\_category |
| Geological Features | Facet, searchable | AND | geologic\_feature |
| Report type | Facet | AND | georesource\_report\_type |
| Data Formats | Facet | AND |  |
| Date | Multi value \(with ranges\) | AND, intersect of date range | dataset\_start\_data, dataset\_completion\_date |
| Access Rights | Facet \(Knowledgebase only\) | OR | extra:access\_rights |

# CKAN Advanced Search
| Attribute | Placeholder | Prefix | Validation | Meta Title |  |
|---|---|---|---|---|---|
| Any attribute | Enter a search term |  | A\-z, 1\-9, space, “\-” | all |  |
| Title | Enter any title | none | A\-z, 1\-9, space, “\-” | title |  |
| Persistent identifier | Enter a Persistent Identifier |  | See persistent identifiers below | extra:identifier |  |
| Report PID | Enter a Report ID | cr | 1\-9 | extra:identifier | Search only dataset type report |
| Survey PID | Enter a Survey Number, e\.g\. ss12345 |  | Two characters or a\-z  plus\+ 0\-9 | extra:identifier | Search only dataset type survey |
| Permit ID | Enter a Permit ID, e\.g\. “EPM12345” | none | A\-z, 1\-9 | resource\_authority\_permit |  |
| Borehole PID | Enter a Borehole PID, e\.g\. bh12345 | bh | 1\-9 | extra:identifier | Search only dataset type borehole |
| Borehole Name | Enter a Borehole Name |  | A\-z, 1\-9, space, “\-” | title | Search only dataset type borehole |
| Borehole Alias | Enter any Borehole Alias  | none | A\-z, 1\-9, space, “\-” | alias | Search only dataset type borehole |


## See also
* 

## License
This code repository's content are licensed under the [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/), the deed of which is stored in this repository here: [LICENSE](LICENSE).


## Contacts
*System owner*:  
**Mark Gordon**  
Geological Survey of Quensland  
Department of Natural Resources, Mines and Energy  
Brisbane, QLD, Australia  
<mark.gordon@dnrme.qld.gov.au>  

*Author*:  
**David Crosswell**  
Enterprise Architect  
Cross-Lateral Enterprises   
<https://crosslateral.com.au>
