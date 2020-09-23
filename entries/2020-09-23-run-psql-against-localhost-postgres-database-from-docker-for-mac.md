---
title: Run psql against localhost postgres database from Docker for Mac
date: 2020-09-23
tags: docker, postgres
---

```shell
docker run -it --rm postgres:alpine psql -h host.docker.internal -U postgres -c 'CREATE DATABASE your_db;'
```
