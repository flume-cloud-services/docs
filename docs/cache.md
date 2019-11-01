---
id: cache
title: Cache
sidebar_label: Cache
---

`Golang key/value Database` via **HTTP** (by Flume Cloud Services)

## Usage

```js
// Create a Flume Instance
const flume = new Flume('admin', 'http://localhost')

// Create the Cache instance with a specific port (leave it blank if there is no specific port)
cache = flume.Cache(5002)

// Connect to the distant File Storage Service
connection = cache.Connect()

// Insert key 'hello' with value 'world'
connection.then(() => cache.Insert('hello', 'world'))
.then(response => console.log(response))
.then(() => cache.Get('hello')) // Get 'hello' key
.then(response => console.log(response))