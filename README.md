# Jitsi Videobridge Zabbix Stats
An simple implementation of Jitsi Videobridge Statistics, to Zabbix. 

Jitsi Videobridge Stats. Based on the built-in Colibri stats API to retrieve statistics from the Jitsi Videobridge (jvb). I've added the most important data, some stats not added, but it is easy to add them by using the Zabbix Server GUI. 

### Preprocessing

The initial version [romantico88/jitsi_videobridge_zabbix_stats](https://github.com/romantico88/jitsi_videobridge_zabbix_stats) used simple UserParameters.

This version should be an improvement using [item value preprocessing](https://www.zabbix.com/documentation/3.4/manual/introduction/whatsnew340#item_value_preprocessing).
That means the agent runs only a single curl request to fetch the complete statistics JSON and the Zabbix server will process it to get the individual item values.

**Note: do not use this template, it is mainly a proof of concept.** I strongly recommend the current version from romantico88, because they switched to preprocessing as well and added a lot more items, graphs, and correct units.

### Full Documentation of Jitsi Videobridge Colibri Stats

See https://github.com/jitsi/jitsi-videobridge/blob/master/doc/statistics.md

### Setup

1. Import the XML template through Zabbix GUI.
2. Add the UserParameter to your Zabbix agent configuration on the videobridge machine (e.g. copy the file userparameter-jitsi.conf to /etc/zabbix_agentd.conf.d/).

### Requirements: 

Install The packet `jq` on zabbix-agent machines:

`apt install jq`

### Versions:

Tested and implemented on Zabbix 4.4, but depending on item value preprocessing it should work on Zabbix versions 3.4.0 and above. If you find a problem, please give me feedback.
