# Getting started

## Prerequisites

- Working recent version of Docker (1.12 and up recommended)

## Starting a local node

Start a local node with the command
```
docker run -d --name antidote -p "8087:8087" antidotedb/antidote:latest
```

This should fetch the Antidote image automatically. For updating to the latest version use the command `docker pull antidotedb/antidote:latest`.

## Building the image locally

For building the Docker image on your local machine, use the following command (must be executed from inside latest directory)
```
docker build -f Dockerfile -t antidotedb-local-build:latest .
```

Then you can run it using:
```
docker run -d --name antidote -p "8087:8087" antidotedb-local-build:latest
```

## Using the local node

Wait until Antidote is ready. The current log can be inspected with `docker logs antidote`. Wait until the log message `Application antidote started on node 'antidote@127.0.0.1'` appears.

Antidote should now be running on port 8087 on localhost.

## Connect to the console

You can connect to the console of a local node typing the following:
```
docker exec -it antidote /opt/antidote/bin/env attach
```
