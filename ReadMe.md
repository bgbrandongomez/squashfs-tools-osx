This is a modified version of `squashfs-tools (1:4.3-3+deb9u1) stretch; urgency=medium`.

It is able to be cross-compiled for Mojave 10.14.2 - OSX.

This is the debian patched version of the source code. I used the command `apt-get source squashfs-tools` to download the source and apply the patches. You can download the sources manually using [Debian's CDN](http://cdn-fastly.deb.debian.org/debian/pool/main/s/squashfs-tools/).

The copyright is GPL-2 as seen in [the license file](LICENSE).

I used sites such as [the OpenViewMobile blog](https://www.openviewmobile.com/2015/10/13/build-squashfs-tools-for-mac-os-x/) and [sigwait's](http://man7.org/linux/man-pages/man3/sigwait.3.html), [sigwaitinfo's](http://man7.org/linux/man-pages/man2/sigwaitinfo.2.html), and [sigtimedwait's](http://man7.org/linux/man-pages/man2/sigtimedwait.2.html) man pages to help me figure out how to modify the source code.

I also changed the Makefile to only compile for LZMA XZ format because I wanted to be able to decompress my router's squashfs filesystem without having to load Virtualbox. The homebrew version of squashfs-tools does not work for me on my Mac.

If you compile this, do know you may have to run the unsquashfs command under sudo to be able to create files owned by root.