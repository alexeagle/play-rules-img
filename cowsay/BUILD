load("@rules_img//img:layer.bzl", "image_layer")
load("@rules_img//img:image.bzl", "image_manifest")
load("@rules_img//img:push.bzl", "image_push")

# Create a layer from files
image_layer(
    name = "app_layer",
    srcs = {
        "/app/bin/server": "//cowsay/cmd/hello",
    },
    compress = "zstd",
)

# Build a container image
image_manifest(
    name = "app_image",
    base = "@distroless_base",
    entrypoint = ["/app/bin/server"],
    layers = [
        ":app_layer",
    ],
)

image_push(
    name = "push",
    image = ":app_image",
    registry = "ttl.sh",
    repository = "{{.BUILD_USER}}/cowsay",
    tag = "24h",
)
