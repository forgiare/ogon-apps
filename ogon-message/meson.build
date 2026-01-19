
moc_files = qt_mod.preprocess(
	moc_headers: ['qogonmessage.h'],
)

ogon_message = executable('ogon-message', 
    'main.cpp', 'qogonmessage.cpp', 'qogonmessage.h', moc_files,
    include_directories: libogon_message_includedir,
    link_with: libogon_message_lib,
    dependencies: [deps_winpr, deps_ogon, deps_qt],
    install: true
)
