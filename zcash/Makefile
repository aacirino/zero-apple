
target_name ?= zcash

include ../Makefile.build

ZERO_VERSION=mac_code_1.0.14-1

zcash_clone:
	if [ ! -d "zero_$(ZERO_VERSION)" ]; then git clone -b $(ZERO_VERSION) https://github.com/cryptoforge/zero.git zero_$(ZERO_VERSION); fi

zcash_config:
	#$(call patchme,zcash_$(ZCASH_VERSION))

zcash_build:
	( cd zero_$(ZERO_VERSION); \
		LIBTOOLIZE=glibtoolize ./zcutil/build.sh --disable-libs -j ${BSPJOB}; \
	)

zcash_install:
	#rm -rf tmp
	#mkdir -p tmp
	#mkdir -p ${BSPINSTALL}/usr/local
	#make DESTDIR=${BSPROOT}/zcash/tmp -C zcash_$(ZCASH_VERSION) install
	#cp -af ${BSPROOT}/zcash/tmp${BSPROOT}/zcash/zcash_$(ZCASH_VERSION)/depends/*/* ${BSPINSTALL}/usr/local
# install zcash init script
	#cp -a files/* ${BSPINSTALL}/usr/local/bin

zcash_uninstall:
	#make -C zcash_$(ZCASH_VERSION) uninstall

zcash_clean:
	#if [ -f "zcash_$(ZCASH_VERSION)/Makefile" ]; then make -C zcash_$(ZCASH_VERSION) distclean; fi

zcash_distclean:
	#rm -rf zcash_$(ZCASH_VERSION)
