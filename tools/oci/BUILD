load("@bazel_skylib//:bzl_library.bzl", "bzl_library")

# no targets in this package

bzl_library(
    name = "go_image",
    srcs = ["go_image.bzl"],
    visibility = ["//visibility:public"],
    deps = [
        "@aspect_bazel_lib//lib:tar",
        "@aspect_bazel_lib//lib:transitions",
        "@rules_oci//oci:defs",
    ],
)
