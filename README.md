 Spark Pipeline

This is a demo of creating a spark ingestion -> aggregation -> storage pipeline.

## Prerequisites

1. Install [Vagrant](https://www.vagrantup.com)
1. Provision your VM

```bash
$ vagrant up
```

## Running Spark

* SSH into your vagrant box `$ vagrant ssh`
* Run spark with docker:

```bash
$ docker run -it -p 8088:8088 -p 8042:8042 -p 8032:8032 -h sandbox sequenceiq/spark bash
```

* then run the spark shell:

```bash
spark-shell \
--master yarn-client \
--driver-memory 1g \
--executor-memory 1g \
--executor-cores 1
```
