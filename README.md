# This repo will house cool, random docker build files.

## content
### compose directory
1. create defaults file
```
docker run -it -e SPLUNK_PASSWORD={password} splunk/splunk:latest create-defaults > default.yml 
```
2. build
```
docker-compose -f {filename.yml} up -d
```
3. teardown
```
docker-compose -f {filename.yml} down
```
#### splunk-M4.yml
splunk SVA M4:
- 1 x multi-site IDXC
    - site1
        - 2 x IDX
    - site2
        - 2 x IDX
- 1 x SHC
    - 5 x SH
    - 1 x deployer

#### cribl-cluster.yml
3-node cribl cluster:
- 1 x leader-node
- 2 x worker-node

#### splunk-S11.yml
{+ update mapped paths to apps per your environment +}

splunk SVA S11:
- 1 x standalone instance
    - 1 x enterprise security 6.6.0
    - 1 x eventgen 7.2.1
    - 1 x BOTS v3
    - 1 x unix TA 8.3.1
    - 1 x tenable TA 5.2.0