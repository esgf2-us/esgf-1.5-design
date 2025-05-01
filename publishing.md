## Publication to ESGF-1.5 index checklist

These `esg-publisher` steps assume familiarity with esg-publisher and some Globus familiarity.  See below for useful links.

 - [] Login to app.globus.org
 - [] Locate the UUID of the index needed to publish (see `indexes.md`)
 - [] Apply for permission for the correct index
 - [] `pip install esgcet==5.3.0b3`
 - [] Modify esg.yaml file with the following settings: 
   ```
   index_node: us-index
   index_UUID: <UUID-for-Target-Index>
   globus_index: true
   ```
 - [] `globus login` with same credentials used above
 -  Run `esgpublish`
   
### Useful links

 - https://esg-publisher.readthedocs.io/
