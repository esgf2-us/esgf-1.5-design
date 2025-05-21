# ESGF-1.5 End-to-End Pre-production Testing

** Testing and validation of Globus Search index metadata and software tools used to publish, search, and browse metadata **

## Testing Elements

1. Publishing to staging + Synchronization to global index using writer and non-admin credentials
- Grant write credential
- Publishing use cases:
    - new Dataset and Files
    - existing Dataset update (includes retracting)
    - existing Dataset and new Files (includes new replicas)
    - existing Dataset update Files
    - existing Dataset remove Files (most likely replicas)
- Run synchronizer

2. Metadata comparison
- Compare Solr and Globus Dataset and File metadata entry counts by project, institute_id, and data_node
- Verify changed metadata attributes match design

3. Discovery from Metragrid, intake-esgf
- Discover datasets and files without replicas
- Discover datasets and files with replicas
- Metagrid Globus Transfer tests
- Metagrid Wget script generation and download

4. Freeze and final synchronizations

5. Final metadata comparison re-run


