#
# NOTE: THIS DOCKERFILE IS GENERATED VIA "apply-templates.sh"
#
# PLEASE DO NOT EDIT IT DIRECTLY.
#

FROM buildpack-deps:bullseye

# ensure local python is preferred over distribution python
ENV PATH /usr/local/bin:$PATH

# http://bugs.python.org/issue19846
# > At the moment, setting "LANG=C" on a Linux system *fundamentally breaks Python 3*, and that's not OK.
ENV LANG C.UTF-8

# CFLAGS
ENV CC="/usr/bin/clang-13" \
    CXX="/usr/bin/clang++-13" \
    CFLAGS="-Qunused-arguments -fdata-sections -ffunction-sections -mllvm -enable-cond-stores-vec -mllvm -slp-vectorize-hor-store -mllvm -enable-loopinterchange -mllvm -enable-loop-distribute -mllvm -enable-unroll-and-jam -mllvm -enable-loop-flatten -mllvm -unroll-runtime-multi-exit -mllvm -aggressive-ext-opt -mllvm -vectorize-loops -mllvm -vectorize-slp -mllvm -extra-vectorizer-passes -mllvm -interleave-small-loop-scalar-reduction -mllvm --isel-rebalance-addr -mllvm --loop-fusion-dependence-analysis=all -mllvm --loop-flatten-widen-iv -fdiagnostics-color=always -pipe -fstack-protector-strong --param ssp-buffer-size=4 -fstack-clash-protection -fslp-vectorize -fvectorize -mfpmath=sse" \
    LDFLAGS="-Wl,-O4 -Wl,-z,now -Wl,-z,relro -Wl,--as-needed -Wl,--no-copy-dt-needed-entries -Wl,--sort-common -Wl,--hash-style=gnu -Wl,--gc-sections"

# runtime dependencies
RUN set -eux; \
	apt-get update; \
	apt-get install -y --no-install-recommends \
		libbluetooth-dev \
		tk-dev \
		uuid-dev \
	; \
	apt-get install -y clang-13; \
	ln -sf /usr/bin/clang-13 /usr/bin/clang; \ 
	ln -sf /usr/bin/clang++-13 /usr/bin/clang++; \
	ln -sf /usr/bin/lld-13 /usr/bin/lld; \
	ln -sf /usr/bin/opt-13 /usr/bin/opt; \
	ln -sf /usr/bin/llvm-objcopy-13 /usr/bin/llvm-objcopy; \
	ln -sf /usr/bin/llvm-objdump-13 /usr/bin/llvm-objdump; \
	ln -sf /usr/bin/llvm-PerfectShuffle-13 	/usr/bin/llvm-PerfectShuffle; \
	ln -sf /usr/bin/llvm-addr2line-13	/usr/bin/llvm-addr2line; \
	ln -sf /usr/bin/llvm-ar-13	/usr/bin/llvm-ar; \
	ln -sf /usr/bin/llvm-as-13	/usr/bin/llvm-as; \
	ln -sf /usr/bin/llvm-bcanalyzer-13	/usr/bin/llvm-bcanalyzer; \
	ln -sf /usr/bin/llvm-bitcode-strip-13	/usr/bin/llvm-bitcode-strip; \
	ln -sf /usr/bin/llvm-c-test-13	/usr/bin/llvm-c-test; \
	ln -sf /usr/bin/llvm-cat-13	/usr/bin/llvm-cat; \
	ln -sf /usr/bin/llvm-cfi-verify-13	/usr/bin/llvm-cfi-verify; \
	ln -sf /usr/bin/llvm-config-13	/usr/bin/llvm-config; \
	ln -sf /usr/bin/llvm-cov-13	/usr/bin/llvm-cov; \
	ln -sf /usr/bin/llvm-cvtres-13	/usr/bin/llvm-cvtres; \
	ln -sf /usr/bin/llvm-cxxdump-13	/usr/bin/llvm-cxxdump; \
	ln -sf /usr/bin/llvm-cxxfilt-13	/usr/bin/llvm-cxxfilt; \
	ln -sf /usr/bin/llvm-cxxmap-13	/usr/bin/llvm-cxxmap; \
	ln -sf /usr/bin/llvm-diff-13	/usr/bin/llvm-diff; \
	ln -sf /usr/bin/llvm-dis-13	/usr/bin/llvm-dis; \
	ln -sf /usr/bin/llvm-dlltool-13	/usr/bin/llvm-dlltool; \
	ln -sf /usr/bin/llvm-dwarfdump-13	/usr/bin/llvm-dwarfdump; \
	ln -sf /usr/bin/llvm-dwp-13	/usr/bin/llvm-dwp; \
	ln -sf /usr/bin/llvm-exegesis-13	/usr/bin/llvm-exegesis; \
	ln -sf /usr/bin/llvm-extract-13	/usr/bin/llvm-extract; \
	ln -sf /usr/bin/llvm-gsymutil-13	/usr/bin/llvm-gsymutil; \
	ln -sf /usr/bin/llvm-ifs-13	/usr/bin/llvm-ifs; \
	ln -sf /usr/bin/llvm-install-name-tool-13	/usr/bin/llvm-install-name-tool; \
	ln -sf /usr/bin/llvm-jitlink-13	/usr/bin/llvm-jitlink; \
	ln -sf /usr/bin/llvm-jitlink-executor-13	/usr/bin/llvm-jitlink-executor; \
	ln -sf /usr/bin/llvm-lib-13	/usr/bin/llvm-lib; \
	ln -sf /usr/bin/llvm-libtool-darwin-13	/usr/bin/llvm-libtool-darwin; \
	ln -sf /usr/bin/llvm-link-13	/usr/bin/llvm-link; \
	ln -sf /usr/bin/llvm-lipo-13	/usr/bin/llvm-lipo; \
	ln -sf /usr/bin/llvm-lto-13	/usr/bin/llvm-lto; \
	ln -sf /usr/bin/llvm-lto2-13	/usr/bin/llvm-lto2; \
	ln -sf /usr/bin/llvm-mc-13	/usr/bin/llvm-mc; \
	ln -sf /usr/bin/llvm-mca-13	/usr/bin/llvm-mca; \
	ln -sf /usr/bin/llvm-ml-13	/usr/bin/llvm-ml; \
	ln -sf /usr/bin/llvm-modextract-13	/usr/bin/llvm-modextract; \
	ln -sf /usr/bin/llvm-mt-13	/usr/bin/llvm-mt; \
	ln -sf /usr/bin/llvm-nm-13	/usr/bin/llvm-nm; \
	ln -sf /usr/bin/llvm-objcopy-13	/usr/bin/llvm-objcopy; \
	ln -sf /usr/bin/llvm-objdump-13	/usr/bin/llvm-objdump; \
	ln -sf /usr/bin/llvm-opt-report-13	/usr/bin/llvm-opt-report; \
	ln -sf /usr/bin/llvm-otool-13	/usr/bin/llvm-otool; \
	ln -sf /usr/bin/llvm-pdbutil-13	/usr/bin/llvm-pdbutil; \
	ln -sf /usr/bin/llvm-profdata-13	/usr/bin/llvm-profdata; \
	ln -sf /usr/bin/llvm-profgen-13	/usr/bin/llvm-profgen; \
	ln -sf /usr/bin/llvm-ranlib-13	/usr/bin/llvm-ranlib; \
	ln -sf /usr/bin/llvm-rc-13	/usr/bin/llvm-rc; \
	ln -sf /usr/bin/llvm-readelf-13	/usr/bin/llvm-readelf; \
	ln -sf /usr/bin/llvm-readobj-13	/usr/bin/llvm-readobj; \
	ln -sf /usr/bin/llvm-reduce-13	/usr/bin/llvm-reduce; \
	ln -sf /usr/bin/llvm-rtdyld-13	/usr/bin/llvm-rtdyld; \
	ln -sf /usr/bin/llvm-sim-13	/usr/bin/llvm-sim; \
	ln -sf /usr/bin/llvm-size-13	/usr/bin/llvm-size; \
	ln -sf /usr/bin/llvm-split-13	/usr/bin/llvm-split; \
	ln -sf /usr/bin/llvm-stress-13	/usr/bin/llvm-stress; \
	ln -sf /usr/bin/llvm-strings-13	/usr/bin/llvm-strings; \
	ln -sf /usr/bin/llvm-strip-13	/usr/bin/llvm-strip; \
	ln -sf /usr/bin/llvm-symbolizer-13	/usr/bin/llvm-symbolizer; \
	ln -sf /usr/bin/llvm-tapi-diff-13	/usr/bin/llvm-tapi-diff; \
	ln -sf /usr/bin/llvm-tblgen-13	/usr/bin/llvm-tblgen; \
	ln -sf /usr/bin/llvm-undname-13	/usr/bin/llvm-undname; \
	ln -sf /usr/bin/llvm-windres-13	/usr/bin/llvm-windres; \
	ln -sf /usr/bin/llvm-xray-13	/usr/bin/llvm-xray; \
	rm -rf /var/lib/apt/lists/*

ENV GPG_KEY A035C8C19219BA821ECEA86B64E628F8D684696D
ENV PYTHON_VERSION 3.10.9

RUN set -eux; \
	\
	savedAptMark="$(apt-mark showmanual)"; \
	apt-get update; \
	apt-get install -y --no-install-recommends \
		patchelf \
	; \
	\
	wget -O python.tar.xz "https://www.python.org/ftp/python/${PYTHON_VERSION%%[a-z]*}/Python-$PYTHON_VERSION.tar.xz"; \
	wget -O python.tar.xz.asc "https://www.python.org/ftp/python/${PYTHON_VERSION%%[a-z]*}/Python-$PYTHON_VERSION.tar.xz.asc"; \
	GNUPGHOME="$(mktemp -d)"; export GNUPGHOME; \
	gpg --batch --keyserver hkps://keys.openpgp.org --recv-keys "$GPG_KEY"; \
	gpg --batch --verify python.tar.xz.asc python.tar.xz; \
	command -v gpgconf > /dev/null && gpgconf --kill all || :; \
	rm -rf "$GNUPGHOME" python.tar.xz.asc; \
	mkdir -p /usr/src/python; \
	tar --extract --directory /usr/src/python --strip-components=1 --file python.tar.xz; \
	rm python.tar.xz; \
	\
	cd /usr/src/python; \
	gnuArch="$(dpkg-architecture --query DEB_BUILD_GNU_TYPE)"; \
	./configure \
		--build="$gnuArch" \
		--enable-loadable-sqlite-extensions \
		--enable-optimizations \
		--enable-option-checking=fatal \
		--enable-shared \
		--with-lto \
		--with-system-expat \
		--without-ensurepip \
	; \
	nproc="$(nproc)"; \
	make -j "$nproc"; \
	make install ; \
	\
# https://github.com/docker-library/python/issues/784
# prevent accidental usage of a system installed libpython of the same version
	bin="$(readlink -vf /usr/local/bin/python3)"; \
	patchelf --set-rpath '$ORIGIN/../lib' "$bin"; \
	\
# enable GDB to load debugging data: https://github.com/docker-library/python/pull/701
	dir="$(dirname "$bin")"; \
	mkdir -p "/usr/share/gdb/auto-load/$dir"; \
	cp -vL Tools/gdb/libpython.py "/usr/share/gdb/auto-load/$bin-gdb.py"; \
	\
	cd /; \
	rm -rf /usr/src/python; \
	\
	find /usr/local -depth \
		\( \
			\( -type d -a \( -name test -o -name tests -o -name idle_test \) \) \
			-o \( -type f -a \( -name '*.pyc' -o -name '*.pyo' -o -name 'libpython*.a' \) \) \
		\) -exec rm -rf '{}' + \
	; \
	\
	ldconfig; \
	\
	apt-mark auto '.*' > /dev/null; \
	apt-mark manual $savedAptMark; \
	apt-get purge -y --auto-remove -o APT::AutoRemove::RecommendsImportant=false; \
	rm -rf /var/lib/apt/lists/*; \
	\
	python3 --version

# make some useful symlinks that are expected to exist ("/usr/local/bin/python" and friends)
RUN set -eux; \
	for src in idle3 pydoc3 python3 python3-config; do \
		dst="$(echo "$src" | tr -d 3)"; \
		[ -s "/usr/local/bin/$src" ]; \
		[ ! -e "/usr/local/bin/$dst" ]; \
		ln -svT "$src" "/usr/local/bin/$dst"; \
	done

# if this is called "PIP_VERSION", pip explodes with "ValueError: invalid truth value '<VERSION>'"
ENV PYTHON_PIP_VERSION 22.3.1
# https://github.com/docker-library/python/issues/365
ENV PYTHON_SETUPTOOLS_VERSION 65.5.1
# https://github.com/pypa/get-pip
ENV PYTHON_GET_PIP_URL https://github.com/pypa/get-pip/raw/66030fa03382b4914d4c4d0896961a0bdeeeb274/public/get-pip.py
ENV PYTHON_GET_PIP_SHA256 1e501cf004eac1b7eb1f97266d28f995ae835d30250bec7f8850562703067dc6

RUN set -eux; \
	\
	wget -O get-pip.py "$PYTHON_GET_PIP_URL"; \
	echo "$PYTHON_GET_PIP_SHA256 *get-pip.py" | sha256sum -c -; \
	\
	export PYTHONDONTWRITEBYTECODE=1; \
	\
	python get-pip.py \
		--disable-pip-version-check \
		--no-cache-dir \
		--no-compile \
		"pip==$PYTHON_PIP_VERSION" \
		"setuptools==$PYTHON_SETUPTOOLS_VERSION" \
	; \
	rm -f get-pip.py; \
	\
	pip --version; \
    pip install --no-cache-dir Cython==3.0.0a11

ENV CFLAGS="$CFLAGS -flto=thin"

CMD ["python3"]