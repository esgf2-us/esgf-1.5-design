# ESGF-1.5 Design

## ESGF-1.5 System Design

![An Architecture Diagram of ESGF-1.5 Catalogs, Software Components, and Metadata load and synchronize processes.](./diagrams/ESGF-1.5%20Design.drawio.png "System Design")


## Metadata Catalogs

- A single ESGF2-US wide Globus Search index operated by US-Globus will contain all the metadata for projects:
  - Read-only: CMIP3, CMIP5, CREATE-IP, E3SM-supplement, GeoMIP, LUCID, TAMIP
  - Synchronized from read-write staging Globus search indexes: CMIP6, CMIP6Plus, DRCDP, E3SM, input4MIPs, obs4MIPs

* Read-write staging Globus search indexes for: CMIP6, CMIP6Plus, DRCDP, E3SM, input4MIPs, obs4MIPs


## Software Components

Existing ESGF-1.0 software components that are being modified for ESGF-1.5:
- esg-publisher
- intake-esgf
- metagrid
- esgf-wget

New ESGF-1.5 software components
- esg_fastapi
- esgf-1.5-metadata-synchronizer

The team will retire this software component:
- The COG component in metagrid will no longer be used

### Metadata Transfer

TBD staff will transfer metadata listed above under Metadata Catalog Changes from Solr to Globus Search indexes:

To ESGF2-US wide Globus Search index:
- Read-only metadata for CMIP3, CMIP5, CREATE-IP, E3SM-supplement, GeoMIP, LUCID, TAMIP will be loaded into the

To ESGF2-US project specific staging Globus Search indexes:
- Read-write metadata for CMIP6, CMIP6Plus, DRCDP, E3SM, input4MIPs, obs4MIPs

The initial transfer, any refreshes, and the final transfer will generate audit that can be inspected by the team and include:
- Date of transfer
- Source Solr index
- Which project or query parameters were used to retrieve metadata
- The target Globus index (staging of public)
- The number of metadata entries process
- The Globus Search ingest ID
- The Globus Search ingest response code

#### Metadata synchronization from staging to ESGF-US wide catalog:
- A configurable synchronizer will be developed between staging and the ESGF-US wide catalog
- This synchronizer will generate the same audit records that the initial/final transfer generated (see above)
- Audit records will be publicly viewable
 
