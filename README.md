```
                     
######  ####  #    # 
    #  #      #    # 
   #    ####  ###### 
  #         # #    # 
 #     #    # #    # 
######  ####  #    # 
                     
```
**Package:** zsh  
**Version:** 5.8-6+deb11u1  
**Priority:** optional  
**Section:** shells  
**Maintainer:** Debian Zsh Maintainers <pkg-zsh-devel@lists.alioth.debian.org>  
**Installed-Size:** 2 526 kB  
**Depends:** zsh-common (= 5.8-6+deb11u1), libc6 (>= 2.29), libcap2 (>= 1:2.10), libtinfo6 (>= 6)  
**Recommends:** libgdbm6 (>= 1.16), libncursesw6 (>= 6), libpcre3  
**Suggests:** zsh-doc  
**Homepage:** https://www.zsh.org/  
**Tag:** devel::interpreter, implemented-in::c, interface::shell,  
 network::client, protocol::ftp, role::program, scope::utility  
**Download-Size:** 908 kB  
**APT-Sources:** http://deb.debian.org/debian bullseye/main amd64 Packages  
**Description:** командная оболочка с большим набором возможностей  
 Zsh — это командный интерпретатор UNIX (shell), используемый как  
 интерактивная оболочка и как оболочка для интерпретатора командных  
 сценариев. Из стандартных оболочек zsh наиболее близок к ksh, но  
 содержит множество расширений. Zsh позволяет редактировать командную  
 строку, имеет встроенную проверку правописания, программируемое дополнение  
 команд, функции оболочки (с автозагрузкой), механизм истории и много  
 других возможностей.  
  
Структура пакета
.

0 directories, 0 files
# Файл preinst
```bash
#!/bin/sh
set -e
# Automatically added by dh_installdeb/13.3.4
dpkg-maintscript-helper symlink_to_dir /usr/share/doc/zsh zsh-common 5.0.7-3 -- "$@"
# End automatically added section
```
# Файл postinst
```bash
#!/bin/sh

set -e

# ksh alternatives
update-alternatives --remove ksh /usr/bin/zsh
update-alternatives --remove ksh /bin/zsh4

# Remove alternatives system for zsh in general
update-alternatives --remove zsh /bin/zsh5
update-alternatives --remove rzsh /bin/zsh5

case "$1" in
    (configure)
        add-shell /bin/zsh
        add-shell /usr/bin/zsh

	# New hardcoded symlinks which unfortunately can't be shipped inside
	# the package itself since some people want to merge /bin and /usr/bin
	# against FHS and all Unix tradition.
	if [ ! -e /usr/bin/zsh -a ! -L /usr/bin/zsh ]; then
	  ln -s /bin/zsh /usr/bin/zsh
	fi
    ;;
    (abort-upgrade|abort-remove|abort-deconfigure)
	exit 0
    ;;
    (*)
	echo "postinst called with unknown argument \`$1'" >&2
	exit 0
    ;;
esac

# Automatically added by dh_installdeb/13.3.4
dpkg-maintscript-helper symlink_to_dir /usr/share/doc/zsh zsh-common 5.0.7-3 -- "$@"
# End automatically added section


exit 0
```
# Файл prerm
```bash
#!/bin/sh
set -e
# Automatically added by dh_installdeb/13.3.4
dpkg-maintscript-helper symlink_to_dir /usr/share/doc/zsh zsh-common 5.0.7-3 -- "$@"
# End automatically added section
```
# Файл postrm
```bash
#!/bin/sh

set -e

case "$1" in
	(remove)
	remove-shell /bin/zsh
	remove-shell /usr/bin/zsh

	# Remove hardcoded symlink again
	if [ -L /usr/bin/zsh ]; then
	  rm -f /usr/bin/zsh
	fi

	;;
esac

# Automatically added by dh_installdeb/13.3.4
dpkg-maintscript-helper symlink_to_dir /usr/share/doc/zsh zsh-common 5.0.7-3 -- "$@"
# End automatically added section

```
