
---
title: gauge.cassandra.ClientRequest.Write.Latency.50thPercentile
brief: 50th percentile (median) of Cassandra write latency
metric_type: gauge
custom: false
---
### gauge.cassandra.ClientRequest.Write.Latency.50thPercentile

50th percentile (median) of Cassandra write latency. This value should
be similar across all nodes in the cluster. If some nodes have higher
values than the rest of the cluster then they may have more connected
clients or may be experiencing heavier than usual compaction load.

