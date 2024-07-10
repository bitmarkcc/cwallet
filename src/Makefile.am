bin_PROGRAMS = cwallet cwallet-gui
cwallet_SOURCES = main.c cwallet.c
cwallet_LDFLAGS = -static
cwallet_gui_SOURCES = main-gui.c cwallet.c
cwallet_gui_LDFLAGS = -static -Wl,-Bdynamic
cwallet_gui_LDADD = $(GTK2_LIBS)
cwallet_gui_CPPFLAGS = $(GTK2_CFLAGS)
