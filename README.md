# retail
 Personal Project 
 Data Generation - I have created simple django application  for three forms customers,products,orders and stored this data in mysql.
 Ingestion pipe - I used adf with self host runtime to copy the data from on-premise mysql data into azure data lake/landing zone.
 raw zone - I have copied the data to raw zone whatever the  data come to landing zone and partitioned by date.

 Trasformed - Here I have Created olap based datasets because the data need to store in snowflake.Once the data arraived then immediatly snowpipe will triggger and loaded data data into snowflake olap tables.
