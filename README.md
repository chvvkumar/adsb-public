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

Screenshot:

![](/Screenshot.png)
