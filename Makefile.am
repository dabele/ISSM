EXTRA_DIST = reconf scripts test m4 examples etc doc packages
SUBDIRS = src

ACLOCAL_AMFLAGS = -I m4

if INSTALL_HEADERS
# install configured headers
issmconfigdir = $(includedir)
issmconfig_HEADERS = \
	./config.h 

# install configured pkg-config file
issmpcdir = $(libdir)/pkgconfig
issmpc_DATA = \
	./ISSM.pc

# install all normal ISSM headers
install-all-issm-headers:
	{ \
	cd $(abs_srcdir)/src/c; \
	hlist=$$(find -name '*.h'); \
	for h in $$hlist; do \
	$(MKDIR_P) $(DESTDIR)$(includedir)/$$(dirname $$h); \
	$(INSTALL_HEADER) $$h $(DESTDIR)$(includedir)/$$h; \
	done; \
	}
.PHONY: install-all-issm-headers
install-data-local: install-all-issm-headers
endif
