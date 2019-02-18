## Install gRPC

```go
go get -u google.golang.org/grpc
```

## Install the protoc plugin for Go

```go
go get -u github.com/golang/protobuf/protoc-gen-go

go install github.com/golang/protobuf/protoc-gen-go

```

## Install protobuf 3 on Ubuntu

```bash
curl -OL https://github.com/protocolbuffers/protobuf/releases/download/v3.7.0rc2/protoc-3.7.0-rc-2-linux-x86_64.zip

# Unzip
unzip protoc-3.7.0-rc-2-linux-x86_64.zip -d protoc3

# Move protoc to /usr/local/bin/
sudo mv protoc3/bin/* /usr/local/bin/

# Move protoc3/include to /usr/local/include/
sudo mv protoc3/include/* /usr/local/include/
```

## Run Proto Buffer Generator 
- Dot means same directory of proto file 
```go
protoc folder_name/file_name.proto --go_out=plugins=grpc:.
example: protoc proto/helloworld.proto --go_out=plugins=grpc:.
```
### if want to change write name of directory
```go
protoc folder_name/file_name.proto --go_out=plugins=grpc:/directory_name
example: protoc proto/helloworld.proto --go_out=plugins=grpc:/proto
```

### Run both server/main.go and client/main.go
```go
go run main.go
```