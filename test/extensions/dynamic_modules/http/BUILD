load(
    "//bazel:envoy_build_system.bzl",
    "envoy_cc_test",
    "envoy_package",
)

licenses(["notice"])  # Apache 2

envoy_package()

envoy_cc_test(
    name = "factory_test",
    srcs = ["factory_test.cc"],
    data = [
        "//test/extensions/dynamic_modules/test_data/c:no_http_config_destory",
        "//test/extensions/dynamic_modules/test_data/c:no_http_config_new",
        "//test/extensions/dynamic_modules/test_data/c:no_op",
    ],
    # factory_context_mocks needs this.
    rbe_pool = "6gig",
    deps = [
        "//source/extensions/filters/http/dynamic_modules:factory_lib",
        "//test/extensions/dynamic_modules:util",
        "//test/mocks/server:factory_context_mocks",
    ],
)

envoy_cc_test(
    name = "filter_test",
    srcs = ["filter_test.cc"],
    data = [
        "//test/extensions/dynamic_modules/test_data/c:no_op",
        "//test/extensions/dynamic_modules/test_data/rust:no_op",
    ],
    # http_mocks needs this.
    rbe_pool = "6gig",
    deps = [
        "//source/extensions/filters/http/dynamic_modules:filter_lib",
        "//test/extensions/dynamic_modules:util",
        "//test/mocks/http:http_mocks",
    ],
)
