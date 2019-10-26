---
id: file-storage
title: File Storage
sidebar_label: File Storage
---

`Golang File Storage` server via **HTTP** (by Flume Cloud Services)

## Usage

```js
// Create a Flume Instance
const flume = new Flume('admin', 'http://localhost')

// Create the File Storage instance with a specific port (leave it blank if there is no specific port)
const fileStorage = flume.FileStorage(5001)

// Connect to the distant File Storage Service
const connection = fileStorage.Connect()
connection.then(() => {

    // Add file to form
    let data = new FormData()
    data.append('file', "This is a file !", 'hello.txt')

    // Post the form
    const fileUpload = fileStorage.PostFile(data)

    // You will get the filename to access it
    fileUpload.then(response => console.log(response))
})
```

If you want to access a private file (need authentication) use `/private/<filename>` (ensure that you are signed in).

Otherwise if you want to access a public file (doesn't need authentication) use `public/<filename>`.