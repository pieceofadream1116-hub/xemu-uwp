xemu_ss.add(files(
  'actions.cc',
  'animation.cc',
  'compat.cc',
  'debug.cc',
  'font-manager.cc',
  'game-library.cc',
  'input-manager.cc',
  'main-menu.cc',
  'main.cc',
  'misc.cc',
  'menubar.cc',
  'monitor.cc',
  'notifications.cc',
  'popup-menu.cc',
  'reporting.cc',
  'scene-components.cc',
  'scene-manager.cc',
  'scene.cc',
  'snapshot-manager.cc',
  'viewport-manager.cc',
  'welcome.cc',
  'widgets.cc',
))

# The imgui subproject only builds its Direct3D 12 backend with MSVC; the
# MSYS2 (GCC) build compiles the same file from here instead.
if d3d12.found() and meson.get_compiler('cpp').get_argument_syntax() != 'msvc'
  xemu_ss.add(files('imgui_impl_dx12.cpp'))
endif

if opengl.found()
  xemu_ss.add(files('gl-helpers.cc'))
else
  xemu_ss.add(files('gl-helpers-stub.cc'))
endif

if host_os == 'windows'
  xemu_ss.add(files('update.cc'))
endif
