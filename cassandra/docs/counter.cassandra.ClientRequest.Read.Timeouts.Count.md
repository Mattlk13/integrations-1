
---
title: counter.cassandra.ClientRequest.Read.Timeouts.Count
brief: Count of read timeouts since server start
metric_type: cumulative
custom: false
---
### counter.cassandra.ClientRequest.Read.Timeouts.Count

Count of read timeouts since server start. This typically indicates a server overload condition.

If this value is increasing across the cluster then the cluster is too small for the application read load.

If this value is increasing for a single server in a cluster, then one of the following conditions may be true:
- one or more clients are directing more load to this server than the others
- the server is experiencing hardware or software issues and may require maintenance.

