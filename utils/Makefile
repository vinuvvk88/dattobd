BINARY_NAME = update-img
INSTALLDIR = $(PREFIX)/bin
SOURCES = update-img.c

.PHONY: shared static install-static install uninstall clean

shared:
	$(CC) $(CCFLAGS) -o $(BINARY_NAME) -L $(BASE_DIR)/lib $(SOURCES) -ldattobd

static:
	$(CC) $(CCFLAGS) -o $(BINARY_NAME) $(SOURCES) $(BASE_DIR)/lib/libdattobd.a

install-static: static
	mkdir -p $(INSTALLDIR)
	install $(BINARY_NAME) $(INSTALLDIR)

install: shared
	mkdir -p $(INSTALLDIR)
	install $(BINARY_NAME) $(INSTALLDIR)

uninstall:
	$(RM) $(INSTALLDIR)/$(BINARY_NAME)

clean:
	$(RM) $(BINARY_NAME)
