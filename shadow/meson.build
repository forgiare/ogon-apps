
moc_files = qt_mod.preprocess(
	moc_headers: ['mainwindow.h', 'sessionmodel.h', 'workerthread.h'],
)

ogon_message = executable('ogon-shadow', 
    'main.cpp', 'mainwindow.cpp', 'sessionmodel.cpp', 'workerthread.cpp', moc_files,
    include_directories: libogon_message_includedir,
    link_with: libogon_message_lib,
    dependencies: [deps_winpr, deps_ogon, deps_qt],
    install: true
)
