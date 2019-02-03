# Run influxDB with collectd on docker

A very simple tutorial to get InfluxDB running on a docker container on a Pi.

The hardware that I used was a Pi3

## Steps
* In my Raspberry Pi 3 host i have created the \influxdb directory to keep the configuration files
and the containers data files.
* Copy over the types.db and influxdb.conf files. The standard influxdb port 8086 as well as 25826 needs to be exposed.

```
		docker run -d -p 8086:8086 -p 25826:25826 \
		-V /influxdb:/var/lib/influxdb \
		-v /influxdb/influxdb.conf:/var/lib/influxdb/influxdb.conf \
		-v /influxdb/types.db:/usr/share/collectd/types.db:ro \
		--restart always
		influxdb
		
```
