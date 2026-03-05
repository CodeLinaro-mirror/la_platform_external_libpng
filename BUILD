load("@rules_cc//cc:cc_library.bzl", "cc_library")
load("@rules_license//rules:license.bzl", "license")

package(
    default_applicable_licenses = [":license"],
)

license(
    name = "license",
    package_name = "libpng",
    copyright_notice = "Copyright (c) 2000-2002, 2004, 2006-2017 Glenn Randers-Pehrson",
    license_kinds = ["@rules_license//licenses/spdx:libpng-2.0"],
    license_text = "LICENSE",
    visibility = ["//visibility:public"],
)

exports_files(["LICENSE"])

cc_library(
    name = "png",
    srcs = [
        "png.c",
        "pngerror.c",
        "pngget.c",
        "pngmem.c",
        "pngpread.c",
        "pngread.c",
        "pngrio.c",
        "pngrtran.c",
        "pngrutil.c",
        "pngset.c",
        "pngtrans.c",
        "pngwio.c",
        "pngwrite.c",
        "pngwtran.c",
        "pngwutil.c",
    ],
    hdrs = [
        "png.h",
        "pngconf.h",
        "pngdebug.h",
        "pnginfo.h",
        "pnglibconf.h",
        "pngpriv.h",
        "pngstruct.h",
    ],
    copts = ["-DPNG_ARM_NEON_OPT=0"],
    includes = ["."],
    linkopts =
        select({
            "@platforms//os:linux": ["-lm"],
            "//conditions:default": [],
        }),
    visibility = ["//visibility:public"],
    deps = ["@zlib"],
)
