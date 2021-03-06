licenses(["notice"])

cc_library(
  name = "acceptor",
  visibility = ["//visibility:public"],
  includes = [
    "upstream",
  ],
  srcs = glob(["upstream/wangle/acceptor/*.cpp"]),
  deps = [
    ":ssl",
    "//third_party/folly:async",
    "//third_party/folly:ssl",
    "//third_party/boost:parameter",
  ]
)

cc_library(
  name = "bootstrap",
  visibility = ["//visibility:public"],
  includes = [
    "upstream",
  ],
  srcs = [
    "upstream/wangle/bootstrap/ServerBootstrap.cpp"
  ],
  deps = [
    "//third_party/folly:async",
    "//third_party/folly:futures",
    "//third_party/boost:parameter",
  ]
)

cc_library(
  name = "channel",
  visibility = ["//visibility:public"],
  includes = [
    "upstream",
  ],
  srcs = glob(["upstream/wangle/channel/*.cpp"]),
  deps = [
    "//third_party/folly:futures",
  ]
)

cc_library(
  name = "concurrent",
  visibility = ["//visibility:public"],
  includes = [
    "upstream",
  ],
  srcs = glob(["upstream/wangle/concurrent/*.cpp"]),
  deps = [
    "//third_party/folly:futures",
  ]
)

cc_library(
  name = "ssl",
  visibility = ["//visibility:public"],
  includes = [
    "upstream",
  ],
  srcs = glob(["upstream/wangle/ssl/*.cpp"]),
  deps = [
    "//third_party/folly:ssl",
  ]
)

# Disabled because dependings on boost/thread
#
# cc_test(
#   name = "bootstrap_test",
#   srcs = [
#     "upstream/wangle/bootstrap/BootstrapTest.cpp"
#   ],
#   deps = [
#     ":wangle",
#     "//third_party/gtest:gtest_main",
#   ]
# )

cc_test(
  name = "concurrent_test",
  srcs = [
    "upstream/wangle/concurrent/test/CodelTest.cpp",
    "upstream/wangle/concurrent/test/GlobalExecutorTest.cpp",
    "upstream/wangle/concurrent/test/ThreadPoolExecutorTest.cpp",
  ],
  deps = [
    ":wangle",
    "//third_party/gtest:gtest_main",
  ]
)

cc_library(
  name = "wangle",
  visibility = ["//visibility:public"],
  deps = [
    ":acceptor",
    ":bootstrap",
    ":channel",
    ":concurrent",
    ":ssl",
  ]
)
