# dbstream
Simple Streaming Platform using PostGres

topic -> Create DATABASE
     partitions -> tables
    retention -> advisory_lock, delete old records

producer
      partition_key -> insert into table_partition values (offsetid, payload)
      batch_size -> internal queue

consumer
      consumer_group -> consumer_group_tbl with offsets, partitions (Last read) --from-beginning
      batch_size -> limit
      owned_partitions -> 
