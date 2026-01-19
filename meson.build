project('ogon-apps', 'c', 'cpp',
       version : '1.0.0',
       license : 'AGPL',
       meson_version : '>= 1.1.0'
)

deps_winpr = dependency('winpr2')
deps_ogon = dependency('ogon1')

qt_ver = 'qt5'
qt_modules = ['Core', 'Gui', 'Widgets',]

deps_qt = dependency(qt_ver, modules: qt_modules,
    #method: 'qmake',  # We force qmake here to be able to use get_variable on Qt variables later
)
qt_mod = import(qt_ver)


translations_dir = join_paths(get_option('prefix'), 'share', qt_ver, 'translations')

add_project_arguments('-DTRANSLATIONS_DIR="@0@"'.format(translations_dir), language: 'cpp')

version = meson.project_version().split('.')
cdata = configuration_data()
cdata.set('OGON_VERSION_MAJOR', version[0])
cdata.set('OGON_VERSION_MINOR', version[1])
cdata.set('OGON_VERSION_REVISION', version[2])
cdata.set('PACKAGE_OGON_MESSAGE_INCLUDE_DIR', join_paths(get_option('prefix'), 'include', 'ogon-message1'))

subdir('libs/ogon-message')
subdir('ogon-message')
subdir('shadow')
