load("@rules_rust//proto:toolchain.bzl", "GRPC_COMPILE_DEPS")
load("@rules_rust//rust:defs.bzl", "rust_binary")
load("@crates//:defs.bzl", "crate")

rust_binary(
    name = "main",
    srcs = ["main.rs"],
)

rust_binary(
    name = "server",
    srcs = ["server.rs"],
    deps = [
        "//:helloworld_proto",
        crate("tonic"),
        crate("tokio"),
        "//:build",
    ] + GRPC_COMPILE_DEPS,
)
