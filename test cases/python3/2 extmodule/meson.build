project('Python extension module', 'c',
  default_options : ['buildtype=release'])
# Because Windows Python ships only with optimized libs,
# we must build this project the same way.

py3_dep = dependency('python3', required : false)

if py3_dep.found()
  subdir('ext')

  test('extmod',
    find_program('blaster.py'),
    env : ['PYTHONPATH=' + pypathdir])
else
  error('MESON_SKIP_TEST: Python3 libraries not found, skipping test.')
endif
