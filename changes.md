# ESGF-1.5 Changes

** Preliminary work in progress list of what is changing between ESGF-1.0 and ESGF-1.5 **

## Metadata Schema Changes

1. The metadata _index_node_ attribute will be set to `us-index` in all metadata entries
2. The metadata _project_ attribute lower case value `cmip3` will be converted to `CMIP3`

## Metadata Catalog Changes

1. There will be a single public ESGF2-US Globus Search index that combines all the Dataset and File metadata from the three Solr indexes at LLNL, ORNL, and ANL
2. The metadata includes references to files on data nodes that are not at LLNL, ORNL, and ANL
3. The metadata includes separate Dataset and File entries for replicas
4. The index will only contain metadata for projects (case sensitive): CMIP3, CMIP5, cmip6, CREATE-IP, DRCDP, e3sm, e3sm-supplement, GeoMIP, input4MIPS2, LUCID, obs4MIPs, and TAMIP
5. There will be publishing-site specific staging Globus Search indexes
  - Containing all the Dataset and File entries that that publishing-site has published or is allowed to update
  - With documented project, institution_id, and data_node values that are in scope for each staging index 
  - At most one publishing-site index can be the authoritative source of metadata entries in the ESGF2-US public index
6. Metadata in ESGF-1.0 projects (case sensivite) NARR_Hydrology, CMIP7, or other future projects will not be available once ESGF-1.0 is retired
7. Metadata from (case sensitive) project mis-published with the wrong case CMIP6 and E3SM, will be discarded
9. The three Solr catalogs in LLNL, ORNL, and ANL will be retired at the end of this project.
10. Catalogs will no longer return metadata in XML format, which is no longer needed by software components that interact with catalogs

## Software Changes

### esg-publisher
1. Change: modified to work with Globus Search
2. Change: modified to publish to a configurable staging Globus Search index or the ESGF2-US public index
3. Change: change retractions to flag File metadata as retracted instead of deleting it

Issues:
- [Implement updates for ESGF-1.5 - esg-publisher#250](https://github.com/ESGF/esg-publisher/issues/250)
- [Update esg-publisher for ESGF-1.5 - esgf-1.5-design#35](https://github.com/esgf2-us/esgf-1.5-design/issues/35)


### metagrid

1. New: search returns datasets, files and replicas hosted on all US based data nodes
   - No code change
2. New version released starting with `v1.5.0`
   - News item to advise users on scope of search to US index


Issues:
- [Implement updates for ESGF-1.5 - metagrid#739](https://github.com/esgf2-us/metagrid/issues/739)
- [Update metagrid for ESGF-1.5 - esgf-1.5-design#36](https://github.com/esgf2-us/esgf-1.5-design/issues/36)
- [Common Query Module? - esgf-1.5-design#25](https://github.com/esgf2-us/esgf-1.5-design/issues/25)
- [Provision Metagrid in production with ESGF-1.5 Public Search Index Support - esgf-1.5-design#50](https://github.com/esgf2-us/esgf-1.5-design/issues/50)


### intake-esgf
1. Change: modified to work with Globus Search
2. New: search returns datasets, files and replicas hosted on all US based data nodes
3. Removed: will no longer be able to return XML metadata

Issues:
- [Implement updates for ESGF-1.5 - intake-esgf#84](https://github.com/esgf2-us/intake-esgf/issues/84)
- [Update intake-esgf for ESGF-1.5 - esgf-1.5-design#37](https://github.com/esgf2-us/esgf-1.5-design/issues/37)


### esg_fastapi (NEW)
1. New: interface to Globus Search used by various components
2. New: search returns datasets, files and replicas hosted on all US based data nodes
3. New: metadata only returned in JSON format

Issues:
- [Update esg_fastapi for ESGF-1.5 esg_fastapi#16](https://github.com/esgf2-us/esg_fastapi/issues/16)
- [Globus search facets do not return all the facet values esg_fastapi#19](https://github.com/esgf2-us/esg_fastapi/issues/19)
- [Solr shard in response inaccurate / misleading esg_fastapi#18](https://github.com/esgf2-us/esg_fastapi/issues/18)
- [Provision ESGF-1.5 esg-fastapi in production - esgf-1.5-design#51](https://github.com/esgf2-us/esgf-1.5-design/issues/51)


### esg-wget API
1. Change: modified to work with Globus Search
2. New: search returns datasets, files and replicas hosted on all US based data nodes

Issues:
- [Implement updates for ESGF-1.5 - esgf-wget#45](https://github.com/ESGF/esgf-wget/issues/45)
- [Update esgf-wget API for ESGF-1.5 - esgf-1.5-design#39](https://github.com/esgf2-us/esgf-1.5-design/issues/39)
- [Common Query Module? - esgf-1.5-design#25](https://github.com/esgf2-us/esgf-1.5-design/issues/25)
- [Provision the ESGF-1.5 esg-wget API in production - esgf-1.5-design#52](https://github.com/esgf2-us/esgf-1.5-design/issues/52)


### esgf-1.5-metadata-synchronizer (NEW)
1. Synchronizes staging Globus Search indexes with the public ESGF2-US wide Globus Search index
2. Only entries in the staging index that can be updated: based on Project and Type Dataset and/of File
3. Retracted Dataset and File entries are synchronized as other metadata, including the retracted flag

Issues:
- [Implement esgf-1.5-metadata-synchronizer - esgf-1.5-design#46](https://github.com/esgf2-us/esgf-1.5-design/issues/46)
- [Final metadata synchronization of the ESGF2-US wide Globus Search index - esgf-1.5-design#41](https://github.com/esgf2-us/esgf-1.5-design/issues/41)
- [Provision ESGF-1.5 synchronizer and status web in production - esgf-1.5-design#53](https://github.com/esgf2-us/esgf-1.5-design/issues/53)


### COG (RETIRED)
1. The COG UI component for data discovery will no longer be used


### Synchronization Audit (NEW)
The initial metadata transfers from Solr to Globus Search,the final production transition metadata transfer, and synchronization between staging indexes and the ESGF2-US public index will generate audit that can be inspected by the team and include:
- Date of metadata transfer
- Source Solr or staging Globus Search index
- Which project or query parameters were used to retrieve metadata
- The target staging of public Globus search index
- The number of Dataset and File metadata entries transfered
- The Globus Search ingest ID
- The Globus Search ingest response code

(Metadata transfer and synchronization site)[https://minxu74.github.io/metadata_docs/]
