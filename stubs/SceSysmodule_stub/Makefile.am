# Copyright (C) 2015 PSP2SDK Project
#
# This Source Code Form is subject to the terms of the Mozilla Public
# License, v. 2.0. If a copy of the MPL was not distributed with this
# file, You can obtain one at http://mozilla.org/MPL/2.0/.

include $(top_srcdir)/stubs/common.mk

PREFIX = _SceSysmodule-0001_
ENTRIES_PREFIX = $(PREFIX)F00_

NIDS = 0x31d87805 0x53099b7a 0x79a0160a

ENTRIES = $(call GET_ENTRIES,$(ENTRIES_PREFIX),$(NIDS))

lib_LIBRARIES = libSceSysmodule_stub.a
libSceSysmodule_stub_a_SOURCES = SceSysmodule_stub.S
am_libSceSysmodule_stub_a_OBJECTS = $(call GET_OBJECTS,$(PREFIX),$(ENTRIES))

$(PREFIX)head.o: $(libSceSysmodule_stub_a_SOURCES)
	$(COMPILE_HEAD)

$(PREFIX)NIDS.o: $(libSceSysmodule_stub_a_SOURCES)
	$(COMPILE_NIDS)

$(ENTRIES): $(libSceSysmodule_stub_a_SOURCES)
	$(call COMPILE_ENTRIES,$(ENTRIES_PREFIX))
