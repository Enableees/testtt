#     #  #####  
##   ## #     # 
# # # # #       
#  #  # #       
#     # #       
#     # #     # 
#     #  #####  
                
**Package:** mc  
**Version:** 3:4.8.26-1.1  
**Priority:** optional  
**Section:** utils  
**Maintainer:** Dmitry Smirnov <onlyjob@debian.org>  
**Installed-Size:** 1 528 kB  
**Provides:** mcedit  
**Depends:** libc6 (>= 2.15), libext2fs2 (>= 1.37), libglib2.0-0 (>= 2.59.2), libgpm2 (>= 1.20.7), libslang2 (>= 2.2.4), libssh2-1 (>= 1.2.8), mc-data (= 3:4.8.26-1.1)  
**Recommends:** mime-support, perl, unzip, sensible-utils  
**Suggests:** arj, bzip2, catdvi | texlive-binaries, dbview, djvulibre-bin, epub-utils, file, genisoimage, gv, imagemagick, libaspell-dev, links | w3m | lynx, odt2txt, poppler-utils, python, python-boto, python-tz, unar, wimtools, xpdf | pdf-viewer, zip  
**Homepage:** https://www.midnight-commander.org  
**Tag:** admin::filesystem, devel::lang:perl, devel::library, implemented-in::c,  
 implemented-in::perl, interface::commandline, interface::text-mode,  
 role::devel-lib, role::program, scope::application, suite::gnu,  
 uitoolkit::ncurses, use::browsing, use::editing, use::organizing,  
 works-with::archive, works-with::file  
**Download-Size:** 534 kB  
**APT-Manual-Installed:** yes  
**APT-Sources:** http://deb.debian.org/debian bullseye/main amd64 Packages  
**Description:** Midnight Commander - многофункциональный диспетчер файлов  
 GNU Midnight Commander – полноэкранный текстовый файловый менеджер.  
 В нём используется двухпанельный интерфейс и встроенная командная оболочка.  
 Также имеется встроенный редактор с подсветкой синтаксиса и просмотрщик,  
 поддерживающий двоичные файлы. Программа поддерживает виртуальную файловую  
 систему (VFS), что позволяет работать с файлами на удалённых машинах  
 (например, на серверах FTP, SSH) и с файлами внутри архивов,  
 как с обычными файлами.  
  
#Структура пакета
.
├── .
├── etc
│   └── mc
│       ├── edit.indent.rc
│       ├── filehighlight.ini
│       ├── mc.default.keymap
│       ├── mc.emacs.keymap
│       ├── mc.ext
│       ├── mc.keymap
│       ├── mc.menu
│       ├── mcedit.menu
│       └── sfs.ini
└── usr
    ├── bin
    │   ├── mc
    │   ├── mcdiff
    │   ├── mcedit
    │   └── mcview
    ├── lib
    │   └── mc
    │       ├── cons.saver
    │       ├── ext.d
    │       │   ├── archive.sh
    │       │   ├── doc.sh
    │       │   ├── image.sh
    │       │   ├── misc.sh
    │       │   ├── package.sh
    │       │   ├── sound.sh
    │       │   ├── text.sh
    │       │   ├── video.sh
    │       │   └── web.sh
    │       ├── extfs.d
    │       │   ├── README
    │       │   ├── README.extfs
    │       │   ├── a+
    │       │   ├── apt+
    │       │   ├── audio
    │       │   ├── bpp
    │       │   ├── changesetfs
    │       │   ├── deb
    │       │   ├── deba
    │       │   ├── debd
    │       │   ├── dpkg+
    │       │   ├── gitfs+
    │       │   ├── hp48+
    │       │   ├── iso9660
    │       │   ├── lslR
    │       │   ├── mailfs
    │       │   ├── patchfs
    │       │   ├── patchsetfs
    │       │   ├── rpm
    │       │   ├── rpms+
    │       │   ├── s3+
    │       │   ├── trpm
    │       │   ├── u7z
    │       │   ├── uace
    │       │   ├── ualz
    │       │   ├── uar
    │       │   ├── uarc
    │       │   ├── uarj
    │       │   ├── uc1541
    │       │   ├── ucab
    │       │   ├── uha
    │       │   ├── ulha
    │       │   ├── ulib
    │       │   ├── unar
    │       │   ├── urar
    │       │   ├── uwim
    │       │   ├── uzip
    │       │   └── uzoo
    │       ├── fish
    │       │   ├── README.fish
    │       │   ├── append
    │       │   ├── chmod
    │       │   ├── chown
    │       │   ├── fexists
    │       │   ├── get
    │       │   ├── hardlink
    │       │   ├── info
    │       │   ├── ln
    │       │   ├── ls
    │       │   ├── mkdir
    │       │   ├── mv
    │       │   ├── rmdir
    │       │   ├── send
    │       │   ├── unlink
    │       │   └── utime
    │       ├── mc-wrapper.csh
    │       ├── mc-wrapper.sh
    │       ├── mc.csh
    │       └── mc.sh
    └── share
        ├── applications
        │   ├── mc.desktop
        │   └── mcedit.desktop
        ├── doc
        │   └── mc
        │       ├── NEWS.Debian.gz
        │       ├── README.Debian
        │       ├── changelog.Debian.gz
        │       ├── changelog.gz
        │       └── copyright
        ├── lintian
        │   └── overrides
        │       └── mc
        ├── mc
        │   └── bin
        │       ├── mc-wrapper.csh
        │       ├── mc-wrapper.sh
        │       ├── mc.csh
        │       └── mc.sh
        └── pixmaps
            ├── mc.xpm
            └── mcedit.xpm

18 directories, 96 files
#Файл preinst
#!/bin/sh
set -e
# Automatically added by dh_installdeb/13.3.4
dpkg-maintscript-helper rm_conffile /etc/mc/edit.spell.rc 3:4.8.5-1 -- "$@"
dpkg-maintscript-helper rm_conffile /etc/mc/mc.charsets 3:4.8-1 -- "$@"
dpkg-maintscript-helper rm_conffile /etc/mc/mc.lib 3:4.8-1 -- "$@"
dpkg-maintscript-helper rm_conffile /etc/mc/Syntax 3:4.8-1 -- "$@"
dpkg-maintscript-helper rm_conffile /etc/mc/mc.menu.sr 3:4.8.17-0 -- "$@"
dpkg-maintscript-helper mv_conffile /etc/mc/cedit.menu /etc/mc/mcedit.menu 3:4.8-1 -- "$@"
dpkg-maintscript-helper mv_conffile /etc/mc/mc.keymap.emacs /etc/mc/mc.emacs.keymap 3:4.8.8-0 -- "$@"
dpkg-maintscript-helper mv_conffile /etc/mc/mc.keymap.default /etc/mc/mc.default.keymap 3:4.8.8-0 -- "$@"
# End automatically added section
#Файл postinst
#!/bin/sh
set -e

case "$1" in
	configure|abort-upgrade)
		update-alternatives --install /usr/bin/view view /usr/bin/mcview 25 \
			--slave /usr/share/man/man1/view.1.gz view.1.gz /usr/share/man/man1/mcview.1.gz
		update-alternatives --install /usr/bin/editor editor /usr/bin/mcedit 25 \
			--slave /usr/share/man/man1/editor.1.gz editor.1.gz /usr/share/man/man1/mcedit.1.gz
	;;
esac

# Automatically added by dh_installdeb/13.3.4
dpkg-maintscript-helper rm_conffile /etc/mc/edit.spell.rc 3:4.8.5-1 -- "$@"
dpkg-maintscript-helper rm_conffile /etc/mc/mc.charsets 3:4.8-1 -- "$@"
dpkg-maintscript-helper rm_conffile /etc/mc/mc.lib 3:4.8-1 -- "$@"
dpkg-maintscript-helper rm_conffile /etc/mc/Syntax 3:4.8-1 -- "$@"
dpkg-maintscript-helper rm_conffile /etc/mc/mc.menu.sr 3:4.8.17-0 -- "$@"
dpkg-maintscript-helper mv_conffile /etc/mc/cedit.menu /etc/mc/mcedit.menu 3:4.8-1 -- "$@"
dpkg-maintscript-helper mv_conffile /etc/mc/mc.keymap.emacs /etc/mc/mc.emacs.keymap 3:4.8.8-0 -- "$@"
dpkg-maintscript-helper mv_conffile /etc/mc/mc.keymap.default /etc/mc/mc.default.keymap 3:4.8.8-0 -- "$@"
# End automatically added section

#Файл prerm
#!/bin/sh
set -e

case "$1" in
	remove)
		update-alternatives --remove editor /usr/bin/mcedit
		update-alternatives --remove view /usr/bin/mcview
	;;
esac

# Automatically added by dh_installdeb/13.3.4
dpkg-maintscript-helper rm_conffile /etc/mc/edit.spell.rc 3:4.8.5-1 -- "$@"
dpkg-maintscript-helper rm_conffile /etc/mc/mc.charsets 3:4.8-1 -- "$@"
dpkg-maintscript-helper rm_conffile /etc/mc/mc.lib 3:4.8-1 -- "$@"
dpkg-maintscript-helper rm_conffile /etc/mc/Syntax 3:4.8-1 -- "$@"
dpkg-maintscript-helper rm_conffile /etc/mc/mc.menu.sr 3:4.8.17-0 -- "$@"
dpkg-maintscript-helper mv_conffile /etc/mc/cedit.menu /etc/mc/mcedit.menu 3:4.8-1 -- "$@"
dpkg-maintscript-helper mv_conffile /etc/mc/mc.keymap.emacs /etc/mc/mc.emacs.keymap 3:4.8.8-0 -- "$@"
dpkg-maintscript-helper mv_conffile /etc/mc/mc.keymap.default /etc/mc/mc.default.keymap 3:4.8.8-0 -- "$@"
# End automatically added section

#Файл postrm
#!/bin/sh
set -e

case "$1" in
	purge)

		rm -f \
			/etc/mc/cedit.menu \
			/etc/mc/*.ini \
			/etc/mc/mc.* \
			/etc/mc/*.rc \
			/etc/mc/Syntax

		rmdir /etc/mc 2>/dev/null || true

	;;
esac

# Automatically added by dh_installdeb/13.3.4
dpkg-maintscript-helper rm_conffile /etc/mc/edit.spell.rc 3:4.8.5-1 -- "$@"
dpkg-maintscript-helper rm_conffile /etc/mc/mc.charsets 3:4.8-1 -- "$@"
dpkg-maintscript-helper rm_conffile /etc/mc/mc.lib 3:4.8-1 -- "$@"
dpkg-maintscript-helper rm_conffile /etc/mc/Syntax 3:4.8-1 -- "$@"
dpkg-maintscript-helper rm_conffile /etc/mc/mc.menu.sr 3:4.8.17-0 -- "$@"
dpkg-maintscript-helper mv_conffile /etc/mc/cedit.menu /etc/mc/mcedit.menu 3:4.8-1 -- "$@"
dpkg-maintscript-helper mv_conffile /etc/mc/mc.keymap.emacs /etc/mc/mc.emacs.keymap 3:4.8.8-0 -- "$@"
dpkg-maintscript-helper mv_conffile /etc/mc/mc.keymap.default /etc/mc/mc.default.keymap 3:4.8.8-0 -- "$@"
# End automatically added section

