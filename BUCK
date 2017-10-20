prebuilt_cxx_library(
    name = 'gtest-pthread',
    header_only = True,
    exported_linker_flags = [
        '-lpthread',
    ],
    visibility = [
        '//googletest:gtest-lib',
    ]
)

cxx_library(
    name = 'gtest-lib',
    srcs = [
        'googletest/src/gtest-all.cc',
    ],
    headers = subdir_glob([
        ('googletest', 'src/*.h'),
        ('googletest', 'src/*.cc'),
    ]),
    exported_headers = subdir_glob([
            ('googletest/include', '**/*.h'),
        ],
        excludes = [
            'googletest/include/internal/**/*.h',
    ]),
    visibility = [
        '//googletest:gtest',
        '//googletest:gmock',
    ],
)

cxx_library(
    name = 'gtest',
    srcs = [
        'googletest/src/gtest_main.cc',
    ],
    exported_deps = [
        ':gtest-lib',
    ],
    visibility = [
        'PUBLIC',
    ]
)

cxx_library(
    name = 'gmock',
    srcs = [
        'googlemock/src/gmock-all.cc',
        'googlemock/src/gmock_main.cc',
    ],
    headers = subdir_glob([
        ('googlemock', 'src/*.cc'),
    ]),
    exported_headers = subdir_glob([
            ('googlemock/include', '**/*.h'),
        ],
        excludes = [
            'googlemock/include/internal/**/*.h',
    ]),
    exported_deps = [
        ':gtest-lib',
    ],
    visibility = [
        'PUBLIC',
    ]
)
