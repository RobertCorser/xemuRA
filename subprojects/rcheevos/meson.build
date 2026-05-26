# Version number mirros rcheevos github release version number
project('rcheevos', 'c', version: '12.3.0')

# List the core C files needed by rcheevos
rcheevos_src = files(
  'src/rc_client_external.c',
  'src/rc_client_raintegration.c',
  'src/rc_client.c',
  'src/rc_compat.c',
  'src/rc_util.c',
  'src/rc_version.c'
  )

rcheevos_rapi_src = files(
    'src/rapi/rc_api_common.c',
    'src/rapi/rc_api_editor.c',
    'src/rapi/rc_api_info.c',
    'src/rapi/rc_api_runtime.c',
    'src/rapi/rc_api_user.c'
    )

rcheevos_rcheevos_src = files(
    'src/rcheevos/alloc.c',
    'src/rcheevos/condition.c',
    'src/rcheevos/condset.c',
    'src/rcheevos/consoleinfo.c',
    'src/rcheevos/format.c',
    'src/rcheevos/lboard.c',
    'src/rcheevos/memref.c',
    'src/rcheevos/operand.c',
    'src/rcheevos/rc_validate.c',
    'src/rcheevos/richpresence.c',
    'src/rcheevos/runtime_progress.c',
    'src/rcheevos/runtime.c',
    'src/rcheevos/trigger.c',
    'src/rcheevos/value.c'
    )

rcheevos_rhash_src = files(
    'src/rhash/aes.c',
    'src/rhash/cdreader.c',
    'src/rhash/hash_disc.c',
    'src/rhash/hash_encrypted.c',
    'src/rhash/hash_rom.c',
    'src/rhash/hash_zip.c',
    'src/rhash/hash.c',
    'src/rhash/md5.c'
    )

rcheevos_src += rcheevos_rapi_src
rcheevos_src += rcheevos_rcheevos_src
rcheevos_src += rcheevos_rhash_src

# Tell meson where the header files live
rcheevos_inc = include_directories('include', 'src', 'src/rapi', 'src/rcheevos', 'src/rhash')

rcheevos_compile_args = ['-DUSE_RETRO_ACHIEVEMENTS', '-DRC_CLIENT_SUPPORTS_HASH']
if host_machine.system() == 'windows'
rcheevos_compile_args += '-DRC_CLIENT_SUPPORTS_RAINTEGRATION'
endif

# Build rcheevos as an internal static library
rcheevos_lib = static_library('rcheevos',
  rcheevos_src,
  include_directories: rcheevos_inc,
  c_args: rcheevos_compile_args
)

# Wrap it up as a dependency object that xemu can inherit
rcheevos_dep = declare_dependency(
  link_with: rcheevos_lib,
  include_directories: rcheevos_inc,
  compile_args: rcheevos_compile_args
)