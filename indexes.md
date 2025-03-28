# ESGF2-US-1.5 Indexes

ESGF2-US-1.5 Globus Search indexes that are replacing legacy Solr indexes at LLNL, ORNL, and ANL.

Current Solr index metagrid interfaces:
- [LLNL Metagrid](https://aims2.llnl.gov/search)
- [ORNL Metagrid](https://esgf-node.ornl.gov/search)
- [ANL Metagrid](https://esgf-node.cels.anl.gov/search)

New ESGF2-US-1.5 Public Catalog metagrid interface:
- Beta Metagrid link needed

## Permissions

Indexes are owned by the Globus group [ESGF2-US-1.5 Index Owners](https://app.globus.org/groups/f2db79d0-fa05-11ef-9082-05baeb3f2fe1/about). 
- ESGF2 staff at Argonne are group administrators

Indexed are administered by the Globus group [ESGF2-US-1.5 Index Administrators](https://app.globus.org/groups/254d7b3e-fa06-11ef-aef6-d7d06b03d9fe/about) 
- ESGF2 staff at Argonne are group administrators
- Min is a group member for metadata transfer from Solr
- Others ESGF2 staff at LLNL, ORNL, or ANL can be made group members as needed

Index administrators should create unique credentials for each publisher-index combination that is authorized to ingest/write to that index.



## Public Index

```
Index ID:     a8ef4320-9e5a-4793-837b-c45161ca1845
Description:  ESGF2-US-1.5 Public Catalog
Display Name: ESGF2-US-1.5-Catalog
Status:       open
Max size:     300 GB
```

## Staging Indexes

Note: these indexes are not in the ESGF expanded resources partition

### E3SM External Publishing
```
Index ID:     f5a2d874-30ef-40a0-8c8d-e2498f3bd026
Description:  ESGF2-US-1.5 private staging for E3SM
Display Name: ESGF2-US-1.5-Staging-E3SM
Status:       open
Max size:     10 GB
```

### NCAR and Canada External Publishing
```
Index ID:     1f385759-596e-4085-8d79-5b1dfedd1ca2
Description:  ESGF2-US-1.5 private staging for CMIP6Plus
Display Name: ESGF2-US-1.5-Staging-CMIP6Plus
Status:       open
Max size:     10 GB
```

### Internal Publishing
```
Index ID:     c7cc5d1e-5740-49c2-aa10-fe31f3bcb035
Description:  ESGF2-US-1.5 private staging for DRCDP
Display Name: ESGF2-US-1.5-Staging-DRCDP
Status:       open
Max size:     1 GB
```

```
Index ID:     3c71c174-c8c8-43e5-994c-10dd4251579a
Description:  ESGF2-US-1.5 private staging for input4MIPs
Display Name: ESGF2-US-1.5-Staging-input4MIPs
Status:       open
Max size:     1 GB
```

```
Index ID:     3cfaa44b-e549-487e-8058-5923aaf095b4
Description:  ESGF2-US-1.5 private staging for obs4MIPs
Display Name: ESGF2-US-1.5-Staging-obs4MIPs
Status:       open
Max size:     1 GB
```

## Staging Indexes Access

Individuals needing to publish to one of the above staging indexes may request it using the following links:
- Join the [ESGF2-US-1.5-Staging-CMIP6Plus Writers](https://app.globus.org/groups/384deb54-0bd7-11f0-9152-0affcb8df433/about) group
- Join the [ESGF2-US-1.5-Staging-DRCDP Writers](https://app.globus.org/groups/347626a4-0bd6-11f0-bbb2-0eb46dc826c9/about) group
- Join the [ESGF2-US-1.5-Staging-E3SM Writers](https://app.globus.org/groups/e59bc7f9-0bd5-11f0-8d3f-0affcb8df433/about) group
- Join the [ESGF2-US-1.5-Staging-input4MIPs Writers](https://app.globus.org/groups/db31c7ec-0bd6-11f0-bdc1-0affc7e5025d) group
- Join the [ESGF2-US-1.5-Staging-obs4MIPs Writers](https://app.globus.org/groups/7168bdf1-0bd6-11f0-908b-0e28c1d8b035) group

Requests will be reviewed before being granted.

## Other Indexes

### Testing Index

Note: this index is not in the ESGF expanded resources partition

```
Index ID:     c0173b0c-5587-437a-a912-ef09b6d14e9c
Description:  ESGF2-US-1.5 Testing Catalog
Display Name: ESGF2-US-1.5-Catalog-Testing
Status:       open
Max size:     100 GB
```

### ORNL Playground
```
Index ID:     ea4595f4-7b71-4da7-a1f0-e3f5d8f7f062
Display Name: ESGF2-ORNL
Status:       open
```

### ANL Playground
```
Index ID:     c123975a-246d-421f-8819-4659edf91e44
Display Name: ESGF2-ANL
Status:       open
```

### Available if needed
```
Index ID:     a37bc34d-de15-493b-9221-b95b13114fd8
Description:  ESGF2-US-1.5 private staging for CMIP6
Display Name: ESGF2-US-1.5-Staging-CMIP6
Status:       open
Max size:     100 GB
```
