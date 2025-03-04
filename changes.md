# ESGF-1.5 Changes

** Preliminary work in progress list of what is changing between ESGF-1.0 and ESGF-1.5 **

## Metadata Schema Changes

1. The metadata _index_node_ attribute will be set to `us-index` in all metadata entries

## Metadata Catalog Changes

1. There will be a single public ESGF2-US Globus Search index with all the metadata for US hosted datasets and files
2. The index will have Type=Dataset entries transfered from the LLNL Solr
3. The index will have Type=File entries from the three LLNL, ORNL, and ANL Solr indexes
4. The index will have Type=File entries for all US based data nodes, including data notes not at LLNL, ORNL, and ANL
5. The index will have one Type=File entry for each file replica on a data node
6. The index will only contain metadata for the CMIP3, CMIP5, CMIP6, CREATE-IP, DRCDP, E3SM, E3SM-supplement, GeoMIP, input4MIPS2, LUCID, obs4MIPs, and TAMIP projects
7. There will be project specific staging Globus Search indexes containing
  - Type=Dataset entries for all datasets in a project
  - Type=File entries for all files in a project
8. Metadata in ESGF-1.0 for NARR_Hydrology, CMIP7, or other future projects will not be available once ESGF-1.0 is retired
9. The three Solr catalogs in LLNL, ORNL, and ANL will be retired at the end of this project.

## Software Changes

### esg-publisher
1. Change: modified to work with Globus Search
2. Change: modified to publish to a configurable staging Globus Search index or the ESGF2-US public index

### metagrid
1. Change: modified to work with Globus Search
2. New: search returns datasets, files and replicas hosted on all US based data nodes
3. Removed: will no longer display XML formatted metadata

### intake-esgf
1. Change: modified to work with Globus Search
2. New: search returns datasets, files and replicas hosted on all US based data nodes
3. Removed: no longer can return XML results

### esg-fastapi (NEW)
1. New: interface to Globus Search used by various components
2. New: search returns datasets, files and replicas hosted on all US based data nodes
3. New: metadata only returned in JSON format

### esg-wget API
1. Change: modified to work with Globus Search
2. New: search returns datasets, files and replicas hosted on all US based data nodes

### esgf-1.5-metadata-synchronizer (NEW)
1. Synchronizes staging Globus Search indexes with the public ESGF2-US wide Globus Search index
2. Only entries in the staging index that can be updated: based on Project and Type Dataset and/of File

### COG (RETIRED)
1. The COG component in metagrid will no longer be used

### Synchronization Audit (NEW)
The initial metadtaa transfers from Solr to Globus Search,the final production transition metadata transfer, and synchronization between staging indexes and the ESGF2-US public index will generate audit that can be inspected by the team and include:
- Date of metadata transfer
- Source Solr or staging Globus Search index
- Which project or query parameters were used to retrieve metadata
- The target staging of pubblic Globus search index
- The number of Dataset and File metadata entries transfered
- The Globus Search ingest ID
- The Globus Search ingest response code

