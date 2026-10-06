## Package management with brew

darina@MacBook-Pro ~ % brew update
<details>
==> Updating Homebrew...
==> Redirected tap kegworks-app/kegworks to tap sikarugir-app/sikarugir
Not trusted tap: kegworks-app/kegworks
Updated 2 taps (homebrew/core and homebrew/cask).
==> New Formulae
maki: Efficient AI coding agent extendable by neovim-like Lua plugins
==> Outdated Formulae
ada-url             icu4c@76            libusb              openjpeg
aom                 icu4c@77            libuv               p11-kit
c-ares              imath               libvidstab          pango
cairo               isl                 libvmaf             pkgconf
capstone            jpeg-turbo          libvpx              pnpm
certifi             jpeg-xl             libx11              postgresql@14
cjson               lame                libxcursor          pugixml
cmake               leptonica           libxext             python@3.13
conan               libarchive          libxfixes           qemu
dav1d               libass              libxfont2           raylib
dtc                 libbluray           libxinerama         sdl2-compat
expat               libdeflate          libxkbfile          simdjson
ffmpeg              libevent            libxmu              snappy
fmt                 libfontenc          libxrandr           srt
fontconfig          libmicrohttpd       little-cms2         svt-av1
freetype            libnghttp2          llhttp              tbb
frei0r              libnghttp3          maven               tesseract
fribidi             libngtcp2           mbedtls             unbound
giflib              libpng              mesa                x265
glfw                librist             mpfr                xauth
glib                libslirp            mpg123              xkbcomp
gnutls              libsm               ncurses             xkeyboard-config
graphite2           libsodium           nettle              xorg-server
harfbuzz            libssh              node                xorgproto
hdrhistogram_c      libtasn1            openexr             yt-dlp
highway             libtiff             openjdk
hwloc               libunibreak         openjdk@17
==> Outdated Casks
fuse-t                     gstreamer-runtime          pgadmin4

You have 106 outdated formulae and 3 outdated casks installed.
You can upgrade them with brew upgrade
or list them with brew outdated.
</details>
darina@MacBook-Pro ~ % brew search nginx
==> Formulae
nginx
darina@MacBook-Pro ~ % brew install nginx
<details>
Warning: The following taps are not trusted:
gcenx/wine
macos-fuse-t/cask
sikarugir-app/sikarugir

Homebrew is currently ignoring formulae, casks and commands
from these taps because tap trust is required.
Prefer trusting only the specific formulae, casks or commands you need.
Trust installed casks from these taps with:
brew trust --cask macos-fuse-t/cask/fuse-t-sshfs
Trust other specific formulae and commands with:
brew trust --formula <user>/<tap>/<formula>
brew trust --command <user>/<tap>/<command>
Whole-tap trust is broader and includes all current and future formulae,
casks and commands from the listed taps. Trust whole taps with:
brew trust gcenx/wine macos-fuse-t/cask sikarugir-app/sikarugir
Untap them with:
brew untap gcenx/wine macos-fuse-t/cask sikarugir-app/sikarugir
For more information, see:
https://docs.brew.sh/Tap-Trust
==> Downloading bottle manifests
✔︎ Bottle Manifest nginx (1.31.6)                    Downloaded   34.8KB/ 34.8KB
==> Would install 1 formula:
nginx 1.31.6
==> Would install 1 dependency for nginx:
openssl@4
==> Do you want to proceed with the installation? [y/n]
Invalid input. Please press 'y' to proceed, or 'n' to abort.
==> Fetching downloads for: nginx
✔︎ Bottle Manifest openssl@4 (4.0.3)                 Downloaded   19.5KB/ 19.5KB
✔︎ Bottle nginx (1.31.6)                             Downloaded    1.6MB/  1.6MB
✔︎ Bottle openssl@4 (4.0.3)                          Downloaded   11.2MB/ 11.2MB
==> Installing nginx dependency: openssl@4
==> Pouring openssl@4--4.0.3.arm64_tahoe.bottle.tar.gz
Unlinking /opt/homebrew/Cellar/openssl@3/3.6.5... 6572 symlinks removed.
🍺  /opt/homebrew/Cellar/openssl@4/4.0.3: 6,820 files, 23.8MB
==> Installing nginx
==> Pouring nginx--1.31.6.arm64_tahoe.bottle.1.tar.gz
🍺  /opt/homebrew/Cellar/nginx/1.31.6: 28 files, 2.8MB
==> Caveats
==> nginx
Docroot is: /opt/homebrew/var/www

The default port has been set in /opt/homebrew/etc/nginx/nginx.conf to 8080 so that
nginx can run without sudo.

nginx will load all files in /opt/homebrew/etc/nginx/servers/.

To start nginx now and restart at login:
brew services start nginx
Or, if you don't want/need a background service you can just run:
/opt/homebrew/opt/nginx/bin/nginx -g daemon\ off\;
</details>
darina@MacBook-Pro ~ % brew info nginx
<details>
==> nginx ✔: stable 1.31.6 (bottled), HEAD
HTTP(S) server and reverse proxy, and IMAP/POP3 proxy server
https://nginx.org/
Installed (on request)
From: https://github.com/Homebrew/homebrew-core/blob/HEAD/Formula/n/nginx.rb
License: BSD-2-Clause
==> Installed Versions
nginx ✔ 1.31.6 (28 files, 2.8MB) [Linked]
==> Dependencies
Required (2): openssl@4 ✔, pcre2 ✔
Recursive Runtime (3): all installed ✔
==> Options
--HEAD
Install HEAD version
==> Caveats
Docroot is: /opt/homebrew/var/www

The default port has been set in /opt/homebrew/etc/nginx/nginx.conf to 8080 so that
nginx can run without sudo.

nginx will load all files in /opt/homebrew/etc/nginx/servers/.

To start nginx now and restart at login:
brew services start nginx
Or, if you don't want/need a background service you can just run:
/opt/homebrew/opt/nginx/bin/nginx -g daemon\ off\;
==> Downloading https://formulae.brew.sh/api/formula/nginx.json
==> Analytics
install: 4,091 (30 days), 21,385 (90 days), 120,431 (365 days)
install-on-request: 4,084 (30 days), 21,330 (90 days), 120,150 (365 days)
build-error: 21 (30 days)
</details>
darina@MacBook-Pro ~ % brew deps nginx
ca-certificates
openssl@4
pcre2
darina@MacBook-Pro ~ % brew list
<details>
==> Formulae
ada-url			libmicrohttpd		openjdk
aom			libnghttp2		openjdk@17
aribb24			libnghttp3		openjpeg
brotli			libngtcp2		openssl@3
c-ares			libogg			openssl@4
ca-certificates		libpng			opus
cairo			librist			p11-kit
capstone		libsamplerate		pango
certifi			libslirp		pcre2
cjson			libsm			pixman
cmake			libsndfile		pkg-config
conan			libsodium		pkgconf
dav1d			libsoxr			pnpm
dtc			libssh			postgresql@14
expat			libtasn1		postgresql@16
ffmpeg			libtiff			pugixml
flac			libudfread		python@3.13
fmt			libunibreak		python@3.14
fontconfig		libunistring		qemu
freetype		libusb			rav1e
frei0r			libuv			raylib
fribidi			libvidstab		readline
gettext			libvmaf			rubberband
giflib			libvorbis		sdl2
git			libvpx			simdjson
glfw			libx11			snappy
glib			libxau			speex
gmp			libxcb			sqlite
gnutls			libxcursor		srt
graphite2		libxdmcp		svt-av1
harfbuzz		libxext			tbb
hdrhistogram_c		libxfixes		tesseract
highway			libxfont2		theora
hwloc			libxinerama		unbound
icu4c			libxkbfile		uvwasi
icu4c@76		libxmu			vde
icu4c@77		libxrandr		webp
icu4c@78		libxrender		x264
imath			libxt			x265
isl			libyaml			xauth
jpeg-turbo		little-cms2		xcb-util
jpeg-xl			llhttp			xcb-util-image
json-c			lz4			xcb-util-keysyms
krb5			lzo			xcb-util-renderutil
lame			maven			xcb-util-wm
leptonica		mbedtls			xkbcomp
libapplewm		mesa			xkeyboard-config
libarchive		mpdecimal		xkeyboardconfig
libass			mpfr			xorg-server
libb2			mpg123			xorgproto
libbluray		ncurses			xvid
libdeflate		nettle			xz
libevent		nginx			yt-dlp
libfontenc		node			zeromq
libice			opencore-amr		zimg
libidn2			openexr			zstd

==> Casks
fuse-t			gstreamer-runtime	pgadmin4
fuse-t-sshfs		kegworks		wineskin
</details>