AM_DEFAULT_SOURCE_EXT = .cpp
AM_CPPFLAGS = -iquote ${top_srcdir}

sbin_PROGRAMS = \
	phosphor-fan-monitor

phosphor_fan_monitor_SOURCES = \
	argument.cpp \
	fan.cpp \
	main.cpp \
	tach_sensor.cpp \
	conditions.cpp

nodist_phosphor_fan_monitor_SOURCES = \
	fan_monitor_defs.cpp

BUILT_SOURCES = fan_monitor_defs.cpp

phosphor_fan_monitor_LDADD = \
	$(top_builddir)/libfan.la \
	$(SDBUSPLUS_LIBS) \
	$(SDEVENTPLUS_LIBS) \
	$(PHOSPHOR_LOGGING_LIBS) \
	${PHOSPHOR_DBUS_INTERFACES_LIBS} \
	-lstdc++fs

phosphor_fan_monitor_CXXFLAGS = \
	$(SDBUSPLUS_CFLAGS) \
	$(SDEVENTPLUS_CFLAGS) \
	$(PHOSPHOR_LOGGING_CFLAGS) \
	${PHOSPHOR_DBUS_INTERFACES_CFLAGS} \
	-flto

fan_monitor_defs.cpp: ${srcdir}/gen-fan-monitor-defs.py
	$(AM_V_GEN)$(GEN_FAN_MONITOR_DEFS)
