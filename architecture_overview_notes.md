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

### Role-based Access Control

automatically generated roles

![](assets\20250821_164459_image.png)

- SHOW GRANTS TO ROLE {name of role}

  ![](assets\20250821_164606_image.png)
- ACCOUNTADMIN has access to Security Admin Role < User Admin role
- One, we learned about securable objects,   roles, privileges, and users.   Two, we learned about   the system defined roles, Org Admin,   account Admin, Security Admin,   user Admin, Sys Admin, public.   Three, we learned how to assume a role.   Four, we learned how to create a new role.   F, we learned how to grant privileges to a role.   Six, we learned how to show   what privileges a role has been granted,   and seven, we learned how to grant a role to a user.   That's a lot of stuff.   We're not quite Arbach black belts,   but we're probably at least Arbach blue belts   or something. Great job.

### Snowpark Dataframes

- library to help transform data
- Python/Java/Scala
- lazy-execution
  - df.show() will not execute until explicitly asked
- saving results to table


### Snowflake Data Engineering


![](assets\20250823_174903_image.png)

### Ingestion


![](assets\20250823_175717_image.png)

### Transformation, Orchestration, and Observability

#### Transformation


![](assets\20250823_175949_image.png)

#### Orchestration

- streams - created on a table and keeps track of changes on table
- tasks - actions on scheduled basis
- ![](assets\20250823_180134_image.png)
-  ![](assets\20250823_180526_image.png)
