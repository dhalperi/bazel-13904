load("@rules_python//python:defs.bzl", "py_binary")
load("@pip//:requirements.bzl", "requirement")

py_binary(
    name = "foo",
    srcs = [":foo.py"],
    deps = [requirement("requests")],
)
