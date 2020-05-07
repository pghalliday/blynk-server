# Blynk Server Docker Image

[![](https://images.microbadger.com/badges/image/mpherg/blynk-server.svg)](http://microbadger.com/images/mpherg/blynk-server
"Get your own image badge on microbadger.com") [![](https://images.microbadger.com/badges/version/mpherg/blynk-server.svg)](http://microbadger.com/images/mpherg/blynk-server
"Get your own version badge on microbadger.com")

Runs your own [Blynk Server](https://github.com/blynkkk/blynk-server) in a Docker container instead of relying on Blynk's public server.

[Blynk](http://www.blynk.cc) is the "first drag-n-drop IoT app builder for Arduino, Raspberry Pi, ESP8266, SparkFun boards, and others." Super fun.

## How To Use It

Easy peasy:

```sh
docker run mpherg/blynk-server:latest
```

To forward IP ports from the host to the container, do this:

```sh
docker run -p 8080:8080 -p 9443:9443 mpherg/blynk-server:latest
```

To persist data, mount a directory into the container:

```sh
docker run -v $(PWD):/data mpherg/blynk-server:latest
```

Custom property files should be mounted in the /blynk folder (next to the blynk server jarfile), eg:

```sh
docker run -v $(PWD)/server.properties:/blynk/server.properties -v $(PWD)/mail.properties:/blynk/mail.properties mpherg/blynk-server:latest
```

Or you can use a data volume in another container (check out different data volume techniques [here](https://docs.docker.com/engine/tutorials/dockervolumes/)).
