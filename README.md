# Geoscience Data Catalogue

# Geoscience Data Catalogue

The GSQ Data Catalogue is index of all geoscience-related data in digital, physical, or federated form.

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
1. **Data Catalogue** – a CKAN-based data catalogue with a number of extensions that improve user experience and performance.
1. **Data Store** - low cost, high volume data object storage (AWS S3 buckets).
1. **Data Schemas** - standardised data models that represent a dataset: its metadata, elements and attributes, and relationships to other datasets and data elements. The data schemas based on DCAT2, ISO, GGIC, PPDM, and other standards.
1. **Controlled Vocabularies** – agreed sets of terms to enable data to be shared and reused across application, enterprise, and community boundaries.
1. **Persistent Identifiers (PID)** – a long-lasting reference to a digital resource such as a document, file, web page, or other object.
1. **Linked Data** – connecting related data so that a person or machine can explore the web of data. With linked data, when you have some of it, you can find other, related, data.

## The 3 data catalogues
1. GSQ Open Data Portal - a freely available catalogue of geoscience data.
1. GSQ Internal Data Portal - an internal catalogue of data that is not yet classified as open data.
1. GSQ Knowledgebase - a data catalogue of GSQ-owned datasets for use by GSQ geoscientists and other departmental users. NOTE: The Knowledgebase and Internal Data Portals are the same CKAN instance.

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



## Work required by the supplier to develop the Data Catalogue:
1.	Data Catalogue:  
    a. Extend and optimise the CKAN Data Catalogue technology platform to enhance functionality, performance, and usability.  
    b. Programmatically populate the data catalogue from existing metadata systems MERLIN, QDEX Reports, QDEX Data, GEM, geochemistry Microsoft Access database.  
    c. Programmatically populate the data catalogue with metadata for geoscience data objects that are not in existing metadata systems, e.g. data on NAS or other storage. This will include activities such as extracting metadata from file header data.  
    d. Optimise the search functionality for the data catalogue. CKAN uses SOLR as its search engine, but we are open to additional search capability, particularly that which allows for facetted searching and the ability to search across specific data attributes across the data store.  
    e. Configure the security of the data catalogue according to the Access Rights security schema: e.g. open access, embargoed access, restricted access, metadata only access.  
2.	Data schemas:  
    a. Assist GSQ staff to create, optimise and extend geoscience data schemas.  
    b. Create schema validations.  
3.	Controlled vocabularies  
    a. Optimise the performance and functionality of the vocabulary management tools. 
    b. Integrate external (non-GSQ) master data sources into the vocabulary manager.  
4.	Persistent identifiers  
    a. Integrate the data catalogue, lodgement forms, and other data collections to existing PID minting services.  
    b. Create PID minting services where no National or State minting service is available.  
    c. Apply PIDs to legacy data as part of data migration to the data catalogue and data lake.  
5.	Linked data  
    a. Assist GSQ staff in the creation, extension, and optimisation of linked data.  
    b. Optimise the performance and end user experience of the graph database to make data more discoverable and interactive.  
    c. Implement visualisations of the linked data.  
    d. Implement APIs to the graph database.  


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
