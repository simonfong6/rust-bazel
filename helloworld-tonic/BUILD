load("@rules_proto//proto:defs.bzl", "proto_library")
load("@rules_rust//proto:proto.bzl", "rust_grpc_library")
load("@crates//:defs.bzl", "crate")
load("@rules_rust//cargo:cargo_build_script.bzl", "cargo_build_script")

package(default_visibility = ["//visibility:public"])

proto_library(
    name = "helloworld",
    srcs = ["proto/helloworld.proto"],
)

rust_grpc_library(
    name = "helloworld_proto",
    visibility = ["//src:__subpackages__"],
    deps = [":helloworld"],
)

cargo_build_script(
    name = "build",
    srcs = ["build.rs"],
    visibility = ["//src:__subpackages__"],
    deps = [crate("tonic-build")],
)
