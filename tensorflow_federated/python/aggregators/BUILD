load("@rules_python//python:defs.bzl", "py_library", "py_test")

package_group(
    name = "default_visibility",
    packages = ["//tensorflow_federated/python/aggregators/..."],
)

package(default_visibility = [":default_visibility"])

licenses(["notice"])

py_library(
    name = "aggregators",
    srcs = ["__init__.py"],
    srcs_version = "PY3",
    visibility = ["//tensorflow_federated:__pkg__"],
)

py_library(
    name = "factory",
    srcs = ["factory.py"],
    srcs_version = "PY3",
    deps = [
        "//tensorflow_federated/python/core/api:computation_types",
        "//tensorflow_federated/python/core/templates:aggregation_process",
    ],
)

py_library(
    name = "sum_factory",
    srcs = ["sum_factory.py"],
    srcs_version = "PY3",
    deps = [
        ":factory",
        "//tensorflow_federated/python/common_libs:py_typecheck",
        "//tensorflow_federated/python/core/api:computation_types",
        "//tensorflow_federated/python/core/api:computations",
        "//tensorflow_federated/python/core/api:intrinsics",
        "//tensorflow_federated/python/core/api:placements",
        "//tensorflow_federated/python/core/templates:aggregation_process",
        "//tensorflow_federated/python/core/templates:measured_process",
    ],
)

py_test(
    name = "sum_factory_test",
    size = "small",
    srcs = ["sum_factory_test.py"],
    python_version = "PY3",
    srcs_version = "PY3",
    deps = [
        ":factory",
        ":sum_factory",
        "//tensorflow_federated/python/common_libs:test",
        "//tensorflow_federated/python/core/api:computation_types",
        "//tensorflow_federated/python/core/api:placements",
        "//tensorflow_federated/python/core/backends/native:execution_contexts",
        "//tensorflow_federated/python/core/templates:aggregation_process",
        "//tensorflow_federated/python/core/templates:measured_process",
    ],
)
