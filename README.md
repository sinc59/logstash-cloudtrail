# Cloudtrail-Logstash

Cloudtrail-Logstash is a docker image to pull AWS Cloudtrail Events from a S3 bucket to logstash.

Why this image ?

  - To publich my first docker image
  - Because at this time the logstash-codec-cloudtrail plugin is not compatible with logstash 5.0

How to use it ?
  - Run this image with appropriate logstash configuration file and add it to /etc/logstash/conf.d/cloudtrail.conf
  - If desired, mount a volume to keep your sincedb file

For example:
```sh
$ docker run --restart always -v $(pwd)/conf/:/etc/logstash/conf.d/ -v $(pwd)/sincedb/:/etc/logstash/sincedb -d sinc59/logstash-cloudtrail

```

