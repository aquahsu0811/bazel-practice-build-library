load("@rules_cc//cc:defs.bzl", "cc_binary", "cc_library")

# Build the shared library

#cc_binary(
#    name = "hellogreet.so",
#    srcs = ["hello-greet.cc", "hello-greet.h"],
#    linkshared = 1,     
#)

cc_library(
    name = "hellogreet.a",
    srcs = ["hello-greet.cc"],
    hdrs = ["hello-greet.h"],
    linkstatic = 1,    
)

# Import the shared library
cc_import(
    name = "imported_hellogreet",
    hdrs = ["hello-greet.h"],
    static_library = "hellogreet.a", ##shared_library
)

# Link to the shared library
cc_binary(
    name = "hello-world",
    srcs = ["hello-world.cc"],
    deps = [
        ":imported_hellogreet",
    ],
)