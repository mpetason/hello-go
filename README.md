### Digital Ocean App Platform Guide

## Setup Github Repository

We need a github repository that we can use to deploy the application. Let's name it "hello-go", for example:

mpetason/hello-go

[Github Guide](https://www.digitalocean.com/community/tutorials/how-to-push-an-existing-project-to-github)

## Create Go Application

Create basic Go Application

```go
package main

import (
        "fmt"
        "net/http"
)

func main() {
        http.HandleFunc("/", HelloServer)
        http.ListenAndServe(":8080", nil)
}

func HelloServer(w http.ResponseWriter, r *http.Request) {
        fmt.Fprintf(w, "Hello World!")
}
```

To use the App Platform there are requirements. We need to run `go mod init` to create a `go.mod` file:

```bash
go mod init USERNAME/hello-go
```

[App Requirements](https://docs.digitalocean.com/products/app-platform/build-system/cloud-native-buildpacks/golang/)


go mod init mpetason/hello-go



## Create App Platform app

Create App 

Select Github

Authorize Github

Choose Repository and branch

Type - Website (don't add database)

Name the site

Select Starter > Launch Starter App

## Cleanup
