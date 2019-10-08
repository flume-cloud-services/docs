---
id: getting-started
title: Getting Started
sidebar_label: Getting Started
---

## Prerequisites

You need to have this installed :

* `Docker Installation`: Docker, Docker-compose
* `Manual Installation`: Golang

## Installation

Get the `docker-compose.yml`

```bash
curl https://raw.githubusercontent.com/flume-cloud-services/flume/master/docker-compose.yml
docker-compose up
```

Use docker compose to launch services
```bash
docker-compose up
```

## Database only

### Docker

```bash
docker run -d -p 8080:8080 flumecloudservices/database
```

### Manually

```bash
mkdir $GOPATH/src/github.com/flume-cloud-services && cd $GOPATH/src/github.com/flume-cloud-services
git clone https://github.com/flume-cloud-services/database.git && cd database
go get -d -v
go install -v

FLUME_DATABASE_ADMIN=admin_name FLUME_DATABASE_SECRET=secret_token database
```

## Cache only

### Docker

```bash
docker run -d -p 8080:8080 flumecloudservices/cache
```

### Manually

```bash
mkdir $GOPATH/src/github.com/flume-cloud-services && cd $GOPATH/src/github.com/flume-cloud-services
git clone https://github.com/flume-cloud-services/cache.git && cd cache
go get -d -v
go install -v

FLUME_CACHE_ADMIN=admin_name FLUME_CACHE_SECRET=secret_token cache
```

## File Storage only

### Docker

```bash
docker run -d -p 8080:8080 flumecloudservices/file-storage
```

### Manually

```bash
mkdir $GOPATH/src/github.com/flume-cloud-services && cd $GOPATH/src/github.com/flume-cloud-services
git clone https://github.com/flume-cloud-services/file-storage.git && cd file-storage
go get -d -v
go install -v

FLUME_FILE_STORAGE_ADMIN=admin_name FLUME_FILE_STORAGE_SECRET=secret_token file-storage
```