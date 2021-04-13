# 간단한 golang gRPC 만들기

## protoc 사용법

```bash
protoc --go-grpc_out=. product_info.proto
```

## product_info.proto

```golang
syntax = "proto3";
package ecommerce;

option go_package = "/ecommerce";

service ProductInfo {
    rpc addProduct(Product) returns (ProductID);
    rpc getProduct(ProductID) returns (Product);
}

message Product {
    string id = 1;
    string name = 2;
    string description = 3;
    float price = 4;
}

message ProductID {
    string value = 1;
}
```
