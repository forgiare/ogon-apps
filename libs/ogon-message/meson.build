
libogon_message_includedir = include_directories('include')

moc_files = qt_mod.preprocess(
	moc_headers: ['include/ogon-message/ogon-message.h'],
)

trans_files = qt_mod.compile_translations(
    ts_files: ['ogon-message_de.ts', 'ogon-message_fr.ts', 'ogon-message_en.ts'],
    install: true,
    install_dir: translations_dir,
) 


libogon_message_lib = library('ogon-message',
    'ogon-message.cpp', moc_files, trans_files,
    include_directories: [libogon_message_includedir],
    dependencies: [deps_winpr, deps_qt, deps_ogon],
    install: true,
)

install_headers(
    ['include/ogon-message/ogon-message.h'],
    install_dir: join_paths(get_option('includedir'), 'ogon-message1', 'ogon-message'),
)

pkgconfig = import('pkgconfig')
pkgconfig.generate(libogon_message_lib,
    filebase: 'ogon-message1',
    name: 'ogon message',
    subdirs: 'ogon-message1',
    description: 'ogon common message library',
    version: meson.project_version(),
    url: 'http://ogon-project.com/',
)

cmake_dir = join_paths(get_option('libdir'), 'cmake', 'ogon-message1')
cmake = import('cmake')
cmake.write_basic_package_version_file(name: 'ogon-message',
	version: meson.project_version(),
	install_dir: cmake_dir
)
cmake.configure_package_config_file(
    name: 'ogon-message',
    input: 'ogon-messageConfig.cmake.in',
    configuration: cdata,
    install_dir: cmake_dir
)
