# HBase With Hive

We will import DATA from 'Hiking' TABLE created on HBase.
visit : https://github.com/SakhriHoussem/HBaseInPractice


```hive
CREATE EXTERNAL TABLE InfoTechnique(key int,distance float, Altitude int)
STORED BY 'org.apache.hadoop.hive.hbase.HBaseStorageHandler'
WITH SERDEPROPERTIES("hbase.columns.mapping"=":key,infoTechnique:distance,infoTechnique:Altitude")
TBLPROPERTIES("hbase.table.name"="hiking");
```


```hive
CREATE EXTERNAL TABLE InfoRandonnee(key INT,nomRando STRING, region STRING, suiteRando INT)
STORED BY 'org.apache.hadoop.hive.hbase.HBaseStorageHandler'
WITH SERDEPROPERTIES("hbase.columns.mapping"=":key,infoHiking:name,infoHiking:region,infoHiking:suiteHiking")
TBLPROPERTIES ("hbase.table.name" = "hiking");
```
