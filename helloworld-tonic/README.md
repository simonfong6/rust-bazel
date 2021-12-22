# Rust GRPC

# Server
In `helloworld-tonic`.
```bash
> cargo run --bin helloworld-server
```

# Client
In a `bash` shell in `helloworld-tonic`. (`zsh` causes issues.)
```bash
> grpcurl -plaintext -import-path ./proto -proto helloworld.proto -d '{"name": "Tonic"}' [::]:50051 helloworld.Greeter/SayHello
{
  "message": "Hello Tonic!"
}
```
