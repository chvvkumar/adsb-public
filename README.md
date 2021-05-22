## RTL-SDR ADS-B Docker Stack using @mikenye 's containers.

Brief explanation of each container and what I use it for:

**Gather ADS-B data from the RTL-SDR V3 and publish it to the other apps as well as push it to InfluxDB (using it's in-built Telegraf). I also use a second container of this image as an MLAT hub:**

https://github.com/mikenye/docker-readsb-protobuf

**Tar1090 for mapping ADS-B Data:**

https://github.com/mikenye/docker-tar1090

**Feeders for various services:**

https://github.com/mikenye/docker-adsbexchange

https://github.com/mikenye/docker-piaware

https://github.com/mikenye/docker-flightradar24

**Grafana:**

Again, modified the excellent dashboard by mikenye

[https://grafana.com/grafana/dashboards/13168](https://grafana.com/grafana/dashboards/13168)

I added an iFrame in Grafana to point to my tar1090 instance like so:

Using the  `Text`  visualization and this iFrame code:

```
<iframe src="https://TAR1090_URL/" title="Map" style="width:100%; height:100%; padding:0; margin:0; border:none;"></iframe>         
```

NOTE: On recent Grafana versions, this parameter needs to be set for Grafana to load an external iFrame:

```
- GF_PANELS_DISABLE_SANITIZE_HTML=true
```

**`.env`  file:**

Fill your specific details for feeders etc. here. The beasthost/port etc. are the names of the containers that run that function.

**Screenshot:**

![](/Screenshot.png)

