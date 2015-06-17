## Recover node with front stress test
### Test list

|name|# of objects|consuming-time|wd|cpt|mq_p|p_mx|p_r|p_s|i_mx|i_r|i_s|
|:---|:-:|:-:|:-:|:-:|--:|--:|--:|--:|--:|--:|--:|  
[20150515_recover_node_1.2.9](20150515_recover_node_1.2.9)|N/A|N/A|No|No|8|10000|5000|250|1000|10|10|
[20150519_recover_node_1.2.9](20150519_recover_node_1.2.9)|N/A|N/A|Yes|Yes|8|10000|5000|250|1000|10|10|
[20150520_recover_node_1.2.9](20150520_recover_node_1.2.9)|N/A|N/A|Yes|Yes|8|10000|5000|250|1000|10|10|
[20150521_recover_node_1.2.10_dev](20150521_recover_node_1.2.10_dev)|N/A|N/A|Yes|Yes|8|10000|5000|250|1000|10|10|
[20150528_recover_node_1.2.10](20150528_recover_node_1.2.10)|N/A|N/A|Yes|Yes|8|10000|5000|250|1000|10|10|
[20150601_recover_node_1.2.10_default](20150601_recover_node_1.2.10_default)|N/A|N/A|Yes|Yes|8|5000|3000|250|1000|10|10|
[20150604_recover_node_1.2.10_default2](20150604_recover_node_1.2.10_default2)|N/A|N/A|Yes|No|8|5000|3000|250|1000|10|10|
[20150612_recover_node_1.2.11-dev](20150612_recover_node_1.2.11-dev)|300000|16.0min|No|Yes|**2**|1000|**100**|10|3000|500|50|
[20150616_recover_node_1.2.11-dev2](20150616_recover_node_1.2.11-dev2)|300000|12.0min|No|Yes|**2**|1000|**200**|10|3000|500|50|
[20150616_recover_node_1.2.11-dev3*](20150616_recover_node_1.2.11-dev3)|300000|7.5min|No|Yes|**8**|1000|**800**|10|3000|500|50|

- wd: Watchdog
- cpt: Auto-Compaction
- mq_p: num of MQ procs
- p_mx: num of batch procs max
- p_r : num of batch procs regular
- p_s: num of batch procs step
- i_mx: interval between batch procs max
- i_r: interval between batch procs regular
- i_s: interval between batch procs step