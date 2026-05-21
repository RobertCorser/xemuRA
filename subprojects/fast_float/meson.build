project('fast_float', 'cpp', version: '8.2.5')

fast_float_include = include_directories('include/fast_float')

fast_float_lib = static_library('fast_float',
    include_directories:fast_float_include
    )

fast_float_dep = declare_dependency(
    link_with:fast_float_lib,
    include_directories: fast_float_include
    )