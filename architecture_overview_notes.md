# Snowflake Architecture Overview

### Core Objects and Architecture

Architecture Layers

![](assets\20250817_190847_snowflake_platform_architecture.png)

#### Optimized Storage

![](assets\20250817_191307_optimized_storage_layer.png)

#### Elastic Multi-Cluster Compute

![](assets\20250817_191526_elastic_multi-cluster_compute.png)

#### Cloud Services

![coud_services.png](./e30a203a44c65040cc4a60ea5237b837.png "coud_services.png")

#### Snowgrid

![snowgrid.png](./2b3cb9e03f863bacd62c8a3866cc3422.png "snowgrid.png")

### Time Travel

* UNDROP and SHOW TABLES uses timetravel
* AT,BEFORE (TIMESTAMPE=>, STATEMENT=>)

### Permanent, Transient, and Temporary Tables

### Cloning

- cloning can be combined with time travel

`---> clone a table based on an offset (so the table as it was at a certain interval in the past)  CREATE OR REPLACE TABLE tasty_bytes.raw_pos.truck_clone_time_travel  CLONE tasty_bytes.raw_pos.truck AT(OFFSET => -60*10); `

### Resource Monitoring

- *account-level monitor* - total credit consumption over all resources in account
- *warehouse-level* - total credit consumption for a particular warehouse
- ![](assets\20250820_192319_image.png)
- creating warehouse-level

  ![](assets\20250820_192427_image.png)
-

### User-Defined Functions (UDFs) - Part I/II


![](assets\20250821_143706_image.png)

- '$$' are called bookends


### User-Defined Table Functions (UDTFs)

- cannot have Scala UTFS
  - can have JavaScript, Python, Java, and SQL
