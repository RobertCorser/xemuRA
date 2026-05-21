achievements_src = files(
    'AchievementManager.cc',
    'AchievementWrapper.cc'
)

achievements_inc = include_directories('.')

achievements_lib = static_library('achievements',
    achievements_src,
    include_directories: achievements_inc,
    dependencies: [ra_common_dep, rcheevos_dep],
    cpp_args: ['-DUSE_RETRO_ACHIEVEMENTS']
    )

achievements_dep = declare_dependency(
    link_with: achievements_lib,
    include_directories: achievements_inc,
    dependencies: [ra_common_dep, rcheevos_dep],
    compile_args: ['-DUSE_RETRO_ACHIEVEMENTS']
    )


# Make sure the dependency object itself is appended to the system source set
specific_ss.add(achievements_dep)
