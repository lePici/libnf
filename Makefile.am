
.NOTPARALLEL:

#EXTRA_DIST = md5sum.sh nfdump-bugs.patch nfdump-thread.patch check_items_map.pl bootstrap prepare-nfdump.sh nfdump
EXTRA_DIST = bootstrap nfdump bzip2 libnf.spec libnf.doxygen


SUBDIRS = src include bin examples 

CLEANFILES = bzip2/*.o bzip2/*.lo nfdump/bin/*.o nfdump/bin/*.lo 
DISTCLEANFILES = bzip2/*.o bzip2/*.lo nfdump/bin/*.o nfdump/bin/*.lo 

#main_SOURCES = nfdump

dist-hook:
	make clean 
	(cd $(distdir) && rm -rf $(DISTCLEANFILES))

.PHONY: rpm
rpm:
	make clean; \
	make dist; \
	rm -rf RPMBUILD; \
	mkdir -p RPMBUILD/{SOURCES,SPECS,BUILD,BUILDROOT,RPMS,SRPMS}; \
	cp libnf.spec RPMBUILD/SPECS; \
	mv libnf-@VERSION@.tar.gz RPMBUILD/SOURCES; \
	rpmbuild -ba RPMBUILD/SPECS/libnf.spec -D "_topdir `pwd`/RPMBUILD"



