load("@rules_python//python:defs.bzl", "py_runtime", "py_runtime_pair")
load("@rules_python//python/pip_install:requirements.bzl", "compile_pip_requirements")

package(
    default_visibility = ["//visibility:public"],
)

constraint_setting(name = "some_constraint")

constraint_value(
    name = "some_constraint_value",
    constraint_setting = ":some_constraint",
)

py_runtime(
    name = "runtime",
    interpreter_path = "C:/Python311/python.exe",
    python_version = "PY3",
)

py_runtime_pair(
    name = "runtime_pair",
    py3_runtime = ":runtime",
)

toolchain(
    name = "some_toolchain",
    exec_compatible_with = [
        ":some_constraint_value",
    ],
    target_compatible_with = [
        ":some_constraint_value",
    ],
    toolchain = ":runtime_pair",
    toolchain_type = "@rules_python//python:toolchain_type",
)

platform(
    name = "some_platform",
    constraint_values = [
        ":some_constraint_value",
    ],
)

compile_pip_requirements(
    name = "requirements",
)
