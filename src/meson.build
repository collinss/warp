pyconf = configuration_data()
pyconf.set('prefix', get_option('prefix'))
pyconf.set('datadir', get_option('datadir'))
pyconf.set('pkgdatadir', install_datadir)
pyconf.set('libexecdir', install_libdir)
pyconf.set('libdir', get_option('libdir'))
pyconf.set('PACKAGE', meson.project_name())
pyconf.set('VERSION', meson.project_version())
pyconf.set('GETTEXT_PACKAGE', meson.project_name())

config_py = configure_file(
  output: 'config.py',
  input: 'config.py.in',
  configuration: pyconf
)

libexec_py = [
  config_py,
  'prefs.py',
  'pulse.py',
  'transfers.py',
  'util.py',
  'warp.py',
]

install_data(libexec_py,
  install_dir: install_libdir
)

data = [
  'warp-window.ui',
]

install_data(data,
  install_dir: install_datadir
)
