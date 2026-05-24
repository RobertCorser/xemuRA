ra_common_src = files(
    'CommonFuncs.cc',
    'FileUtil.cc',
    'HttpRequest.cc',
    'IOFile.cc',
    'StringUtil.cc',
    'Thread.cc'
)

ra_common_inc = include_directories('.')

ra_common_lib = static_library('ra_common',
    ra_common_src,
    include_directories: ra_common_inc,
    dependencies: [fmt_dep, curl]
    )

ra_common_dep = declare_dependency(
    link_with: ra_common_lib,
    include_directories: ra_common_inc
    )

specific_ss.add(ra_common_dep)

specific_ss.add(fast_float_dep)