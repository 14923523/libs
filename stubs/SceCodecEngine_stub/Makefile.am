# Copyright (C) 2015 PSP2SDK Project
#
# This Source Code Form is subject to the terms of the Mozilla Public
# License, v. 2.0. If a copy of the MPL was not distributed with this
# file, You can obtain one at http://mozilla.org/MPL/2.0/.

include $(top_srcdir)/stubs/common.mk

PREFIX = _SceCodecEngine-0001_
ENTRIES_PREFIX = $(PREFIX)F00_

NIDS = 0x1a3a53e5 0x6a31831d 0x95ea3b3e 0xf0b4c892

ENTRIES = $(call GET_ENTRIES,$(ENTRIES_PREFIX),$(NIDS))

lib_LIBRARIES = libSceCodecEngine_stub.a
libSceCodecEngine_stub_a_SOURCES = SceCodecEngineUser_stub.S
am_libSceCodecEngine_stub_a_OBJECTS = $(call GET_OBJECTS,$(PREFIX),$(ENTRIES))

$(PREFIX)head.o: $(libSceCodecEngine_stub_a_SOURCES)
	$(COMPILE_HEAD)

$(PREFIX)NIDS.o: $(libSceCodecEngine_stub_a_SOURCES)
	$(COMPILE_NIDS)

$(ENTRIES): $(libSceCodecEngine_stub_a_SOURCES)
	$(call COMPILE_ENTRIES,$(ENTRIES_PREFIX))
