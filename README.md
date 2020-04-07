# jitsi_videobridge_zabbix_stats
An simple implementation of Jitsi Videobridge Statics from Colibri module, to Zabbix. 

Jitsi Videobridge Stats. Based on Colibri stats bulit-in api to present Staticis from Jitsi Videobridge.

Full Doc of Colibri stats

`https://github.com/jitsi/jitsi-videobridge/blob/master/doc/statistics.md`

1. Add the xml template to throughout Zabbix GUI.
2. Add in following zabbix UserParameters on videobridge machine with installed zabbix-agent:

```
UserParameter=jvb.stats[*],curl -s curl -s http://localhost:8080/colibri/stats | jq '.$1'
```

Requirements: 

Install The packet `jq` on zabbix-agent machines:

`apt install jq`

Versions:

Tested and implemated on Zabbix 4.2, but i depending on Simple UserParameter architecture (based on curl an jq) it should works on older Versions.
