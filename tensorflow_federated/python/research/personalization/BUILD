load("@rules_python//python:defs.bzl", "py_binary", "py_library", "py_test")

package(default_visibility = ["//tensorflow_federated/python/research"])

licenses(["notice"])

py_library(
    name = "p13n_utils",
    srcs = ["p13n_utils.py"],
    srcs_version = "PY3",
)

py_test(
    name = "p13n_utils_test",
    srcs = ["p13n_utils_test.py"],
    python_version = "PY3",
    srcs_version = "PY3",
    deps = [
        ":p13n_utils",
        "//tensorflow_federated",
    ],
)

py_binary(
    name = "run_emnist_p13n",
    srcs = ["run_emnist_p13n.py"],
    python_version = "PY3",
    srcs_version = "PY3",
    deps = [
        ":p13n_utils",
        "//tensorflow_federated",
        "//tensorflow_federated/python/research/utils/models:emnist_models",
    ],
)
