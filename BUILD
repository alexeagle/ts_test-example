filegroup(
    name = "node_modules",
    # Only include files needed for type-checking and runtime
    srcs = glob([
        "node_modules/**/*.js",
        "node_modules/**/*.d.ts",
        "node_modules/**/*.json",
        "node_modules/karma/bin/karma",
    ]),
    visibility = ["//visibility:public"],
)

load("@build_bazel_rules_typescript//:defs.bzl", "ts_library", "ts_test")

ts_library(
    name = "decrement",
    srcs = ["decrement.ts"],
)

ts_library(
    name = "decrement_tests",
    srcs = ["decrement.spec.ts"],
    deps = [":decrement"],
    testonly = 1,
)

ts_library(
    name = "increment",
    srcs = ["increment.ts"],
)

ts_library(
    name = "increment_tests",
    srcs = ["increment.spec.ts"],
    deps = [":increment"],
    testonly = 1,
)

ts_test(
    name = "decrement_test",
    deps = [
      ":decrement_tests",
    ],
)

ts_test(
    name = "increment_test",
    deps = [
      ":increment_tests",
    ],
)
