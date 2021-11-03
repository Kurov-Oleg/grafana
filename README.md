# grafana

1. for disk: 100-((node_filesystem_avail_bytes*100)/node_filesystem_size_bytes)
2. for cpu:100 * (1-avg by (instance) (irate(node_cpu_seconds_total{mode='idle'}[1m])))
3. for cpu la 1: avg (node_load1)/count(count(node_cpu_seconds_total)by(cpu))*100
4. for cpu la 5: avg (node_load5)/count(count(node_cpu_seconds_total)by(cpu))*100
5. for cpu la 15: avg (node_load15)/count(count(node_cpu_seconds_total)by(cpu))*100
6. for mem: ((node_memory_MemTotal_bytes-node_memory_MemFree_bytes)/(node_memory_MemTotal_bytes))*100
