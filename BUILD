load("@bazel_skylib//rules:common_settings.bzl", "string_flag")

genrule(
    name = "sample",
    outs = ["out.txt"],
    cmd = select({
        "//:dev_build": "echo dev && echo dev > $@",
        "//:prod_build": "echo prod && echo prod > $@",
    }),
)

string_flag(
    name = "env",
    build_setting_default = "dev",
    values = [
        "dev",
        "prod",
    ],
)

config_setting(
    name = "dev_build",
    flag_values = {":env": "dev"},
)

config_setting(
    name = "prod_build",
    flag_values = {":env": "prod"},
)
