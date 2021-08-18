# Presto Usage

**Run Presto db Sandbox**
```
docker run -p 8080:8080 --name presto ahanaio/prestodb-sandbox
```

**Run CLI**
```
docker exec -it presto  presto-cli
```

**Commands**

*Show Catalogs*
```
presto> show catalogs;

 Catalog
---------
 jmx
 memory
 system
 tpcds
 tpch
(5 rows)

Query 20210818_010403_00009_dxqzj, FINISHED, 1 node
Splits: 19 total, 19 done (100.00%)
461ms [0 rows, 0B] [0 rows/s, 0B/s
```

*Show schemas*
```
presto> show schemas in tpcds;
       Schema
--------------------
 information_schema
 sf1
 sf10
 sf100
 sf1000
 sf10000
 sf100000
 sf300
 sf3000
 sf30000
 tiny
(11 rows)

Query 20210818_010507_00010_dxqzj, FINISHED, 1 node
Splits: 19 total, 19 done (100.00%)
263ms [11 rows, 128B] [41 rows/s, 487B/s]
```

**Set a schema and catalog**

```
presto> use tpcds.sf10;
USE

presto:sf10> show tables;
         Table
------------------------
 call_center
 catalog_page
 catalog_returns
 catalog_sales
 customer
 customer_address
 customer_demographics
 date_dim
 dbgen_version
 household_demographics
 income_band
 inventory
 item
 promotion
 reason
 ship_mode
 store
 store_returns
 store_sales
 time_dim
 warehouse
 web_page
 web_returns
 web_sales
 web_site
(25 rows)

Query 20210818_010603_00012_dxqzj, FINISHED, 1 node
Splits: 19 total, 19 done (100.00%)
315ms [25 rows, 619B] [79 rows/s, 1.92KB/s]
```

# References

* https://hub.docker.com/r/ahanaio/prestodb-sandbox
* https://prestodb.io/docs/current/sql.html
* https://www.youtube.com/watch?v=67gXN5697Vw&ab_channel=FacebookDevelopers
