cargs = ['-DG_LOG_DOMAIN="FuPluginFastboot"']
plugins += {meson.current_source_dir().split('/')[-1]: true}

plugin_quirks += files('fastboot.quirk')
plugin_builtins += static_library('fu_plugin_fastboot',
  sources: [
    'fu-fastboot-plugin.c',
    'fu-fastboot-device.c',
  ],
  include_directories: plugin_incdirs,
  link_with: plugin_libs,
  c_args: cargs,
  dependencies: plugin_deps,
)

if not supported_build
  plugin_quirks += files('ci.quirk')
  enumeration_data += files('tests/fastboot-google-sargo-setup.json')
  device_tests += files('tests/fastboot-google-sargo.json')
endif
