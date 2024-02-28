# OS-Linux-commands-Shell-scripting
Operating systems Lab exercise
# Linux commands-Shell scripting
Linux commands-Shell scripting

# AIM:
To practice Linux Commands and Shell Scripting

# DESIGN STEPS:

### Step 1:

Navigate to any Linux environment installed on the system or installed inside a virtual environment like virtual box/vmware or online linux JSLinux (https://bellard.org/jslinux/vm.html?url=alpine-x86.cfg&mem=192) or docker.

### Step 2:

Execute the following commands

### Step 3:

Testing the commands for the desired output. 

# COMMANDS:
### Create the following files file1, file2 as follows:
cat > file1
```
chanchal singhvi
c.k. shukla
s.n. dasgupta
sumit chakrobarty
^d
```
cat > file2
```
anil aggarwal
barun sengupta
c.k. shukla
lalit chowdury
s.n. dasgupta
^d
```
### Display the content of the files

cat < file1

## OUTPUT
```
chanchal singhvi
c.k. shukla
s.n. dasgupta
sumit chakrobarty
^d
```

cat < file2
## OUTPUT

```
chanchal singhvi
c.k. shukla
s.n. dasgupta
sumit chakrobarty
```

# Comparing Files

cmp file1 file2

## OUTPUT
```
file1 file2 differ: byte 1, line 1
```

comm file1 file2

 ## OUTPUT
```
anil aggarwal
	barun sengupta
chanchal singhvi
		c.k. shukla
	lalit chowdury
		s.n. dasgupta
sumit chakrobarty
```
 
diff file1 file2

## OUTPUT

```
1c1,2
< chanchal singhvi
---
> anil aggarwal
> barun sengupta
2a4
> lalit chowdury
4d5
< sumit chakrobarty
```

#Filters

### Create the following files file11, file22 as follows:

cat > file11
```
Hello world
This is my world
^d
```
cat > file22
```
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
^d
```

cut -c1-3 file11

## OUTPUT
```
Hel
Thi
```
cut -d "|" -f 1 file22

## OUTPUT
```
1001 
1001 
1002 
1003 
1005 
1004 
```
cut -d "|" -f 2 file22

## OUTPUT

```
Ram 
Ram 
tom 
Joe 
Sam 
Sit 
```

cat < newfile 
```
Hello world
hello world
^d
````
cat > newfile 
```
Hello world
hello world
```
 
grep Hello newfile 

## OUTPUT

```
Hello world
```

grep hello newfile 

## OUTPUT

```
hello world
```

grep -v hello newfile 

## OUTPUT

```
Hello world
Linux is world number 1
Unix is predecessor
Linux is best in this World
```

cat newfile | grep -i "hello"
## OUTPUT

```
Hello world
hello world
```

cat newfile | grep -i -c "hello"

## OUTPUT

```
2
```

grep -R ubuntu /etc

## OUTPUT

```
/etc/apparmor.d/abstractions/ubuntu-email:# Users of this abstraction need to include the ubuntu-helpers abstraction
/etc/apparmor.d/abstractions/ubuntu-email:#   include <abstractions/ubuntu-helpers>
/etc/apparmor.d/abstractions/ubuntu-email:  include if exists <abstractions/ubuntu-email.d>
/etc/apparmor.d/abstractions/ubuntu-feed-readers:# Users of this abstraction need to include the ubuntu-helpers abstraction
/etc/apparmor.d/abstractions/ubuntu-feed-readers:#   include <abstractions/ubuntu-helpers>
/etc/apparmor.d/abstractions/ubuntu-feed-readers:  include if exists <abstractions/ubuntu-feed-readers.d>
/etc/apparmor.d/abstractions/ubuntu-bittorrent-clients:# Users of this abstraction need to include the ubuntu-helpers abstraction
/etc/apparmor.d/abstractions/ubuntu-bittorrent-clients:#   include <abstractions/ubuntu-helpers>
/etc/apparmor.d/abstractions/ubuntu-bittorrent-clients:  include if exists <abstractions/ubuntu-bittorrent-clients.d>
/etc/apparmor.d/abstractions/ubuntu-xterm:  include if exists <abstractions/ubuntu-xterm.d>
/etc/apparmor.d/abstractions/ubuntu-browsers:# Users of this abstraction need to include the ubuntu-helpers abstraction
/etc/apparmor.d/abstractions/ubuntu-browsers:#   include <abstractions/ubuntu-helpers>
/etc/apparmor.d/abstractions/gvfs-open:#   # needed for ubuntu-* abstractions
/etc/apparmor.d/abstractions/gvfs-open:#   include <abstractions/ubuntu-helpers>
/etc/apparmor.d/abstractions/gvfs-open:#   include <abstractions/ubuntu-browsers>
/etc/apparmor.d/abstractions/gvfs-open:#   include <abstractions/ubuntu-email>
/etc/apparmor.d/abstractions/ubuntu-browsers.d/productivity:# Users of this abstraction need to include the ubuntu-helpers abstraction
/etc/apparmor.d/abstractions/ubuntu-browsers.d/productivity:#   include <abstractions/ubuntu-helpers>
/etc/apparmor.d/abstractions/ubuntu-browsers.d/mailto:  include <abstractions/ubuntu-email>
/etc/apparmor.d/abstractions/ubuntu-browsers.d/mailto:  include <abstractions/ubuntu-console-email>
/etc/apparmor.d/abstractions/ubuntu-browsers.d/mailto:  include <abstractions/ubuntu-gnome-terminal>
/etc/apparmor.d/abstractions/ubuntu-browsers.d/multimedia:# Users of this abstraction need to include the ubuntu-helpers abstraction
/etc/apparmor.d/abstractions/ubuntu-browsers.d/multimedia:#   include <abstractions/ubuntu-helpers>
/etc/apparmor.d/abstractions/ubuntu-browsers.d/multimedia:  include <abstractions/ubuntu-media-players>
/etc/apparmor.d/abstractions/ubuntu-browsers.d/multimedia:  include <abstractions/ubuntu-bittorrent-clients>
/etc/apparmor.d/abstractions/ubuntu-browsers.d/multimedia:  include <abstractions/ubuntu-feed-readers>
/etc/apparmor.d/abstractions/ubuntu-browsers.d/plugins-common:  # Since all the ubuntu-browsers.d abstractions need this, just include it
/etc/apparmor.d/abstractions/ubuntu-browsers.d/plugins-common:  include <abstractions/ubuntu-helpers>
/etc/apparmor.d/abstractions/ubuntu-browsers.d/chromium-browser:include <abstractions/ubuntu-browsers.d/plugins-common>
/etc/apparmor.d/abstractions/ubuntu-browsers.d/chromium-browser:include <abstractions/ubuntu-browsers.d/mailto>
/etc/apparmor.d/abstractions/ubuntu-browsers.d/chromium-browser:include <abstractions/ubuntu-browsers.d/multimedia>
/etc/apparmor.d/abstractions/ubuntu-browsers.d/chromium-browser:include <abstractions/ubuntu-browsers.d/productivity>
/etc/apparmor.d/abstractions/ubuntu-browsers.d/chromium-browser:include <abstractions/ubuntu-browsers.d/java>
/etc/apparmor.d/abstractions/ubuntu-browsers.d/chromium-browser:include <abstractions/ubuntu-browsers.d/kde>
/etc/apparmor.d/abstractions/ubuntu-browsers.d/chromium-browser:include <abstractions/ubuntu-browsers.d/text-editors>
/etc/apparmor.d/abstractions/ubuntu-browsers.d/chromium-browser:include <abstractions/ubuntu-browsers.d/ubuntu-integration>
/etc/apparmor.d/abstractions/ubuntu-browsers.d/chromium-browser:include <abstractions/ubuntu-browsers.d/user-files>
/etc/apparmor.d/abstractions/ubuntu-browsers.d/text-editors:# Users of this abstraction need to include the ubuntu-helpers abstraction
/etc/apparmor.d/abstractions/ubuntu-browsers.d/text-editors:#   include <abstractions/ubuntu-helpers>
/etc/apparmor.d/abstractions/ubuntu-browsers.d/ubuntu-integration:# Users of this abstraction need to include the ubuntu-helpers abstraction
/etc/apparmor.d/abstractions/ubuntu-browsers.d/ubuntu-integration:#   include <abstractions/ubuntu-helpers>
/etc/apparmor.d/abstractions/ubuntu-browsers.d/ubuntu-integration:  # Kubuntu
/etc/apparmor.d/abstractions/ubuntu-browsers.d/kde:# Users of this abstraction need to include the ubuntu-helpers abstraction
/etc/apparmor.d/abstractions/ubuntu-browsers.d/kde:#   include <abstractions/ubuntu-helpers>
/etc/apparmor.d/abstractions/ubuntu-konsole:  include if exists <abstractions/ubuntu-konsole.d>
/etc/apparmor.d/abstractions/ubuntu-unity7-base:  include if exists <abstractions/ubuntu-unity7-base.d>
/etc/apparmor.d/abstractions/gio-open:#   # needed for ubuntu-* abstractions
/etc/apparmor.d/abstractions/gio-open:#   include <abstractions/ubuntu-helpers>
/etc/apparmor.d/abstractions/gio-open:#   include <abstractions/ubuntu-browsers>
/etc/apparmor.d/abstractions/gio-open:#   include <abstractions/ubuntu-email>
/etc/apparmor.d/abstractions/ubuntu-unity7-launcher:  include if exists <abstractions/ubuntu-unity7-launcher.d>
/etc/apparmor.d/abstractions/ubuntu-unity7-messaging:  include if exists <abstractions/ubuntu-unity7-messaging.d>
/etc/apparmor.d/abstractions/ubuntu-console-browsers:# include <abstractions/ubuntu-gnome-terminal>
/etc/apparmor.d/abstractions/ubuntu-console-browsers:# Users of this abstraction need to include the ubuntu-helpers abstraction
/etc/apparmor.d/abstractions/ubuntu-console-browsers:#   include <abstractions/ubuntu-helpers>
/etc/apparmor.d/abstractions/ubuntu-console-browsers:  include if exists <abstractions/ubuntu-console-browsers.d>
/etc/apparmor.d/abstractions/ubuntu-media-players:# Users of this abstraction need to include the ubuntu-helpers abstraction
/etc/apparmor.d/abstractions/ubuntu-media-players:#   include <abstractions/ubuntu-helpers>
/etc/apparmor.d/abstractions/ubuntu-media-players:  include if exists <abstractions/ubuntu-media-players.d>
/etc/apparmor.d/abstractions/ubuntu-gnome-terminal:  include if exists <abstractions/ubuntu-gnome-terminal.d>
/etc/apparmor.d/abstractions/evince:  #include <abstractions/ubuntu-helpers>
/etc/apparmor.d/abstractions/evince:  # Lubuntu
/etc/apparmor.d/abstractions/evince:  /etc/xdg/lubuntu/applications/defaults.list r,
/etc/apparmor.d/abstractions/exo-open:#   # needed for ubuntu-* abstractions
/etc/apparmor.d/abstractions/exo-open:#   include <abstractions/ubuntu-helpers>
/etc/apparmor.d/abstractions/exo-open:#   include <abstractions/ubuntu-browsers>
/etc/apparmor.d/abstractions/exo-open:#   include <abstractions/ubuntu-email>
/etc/apparmor.d/abstractions/exo-open:  /usr/share/{xfce{,4},xubuntu}/applications/{,*.list} r,
/etc/apparmor.d/abstractions/ubuntu-console-email:# include <abstractions/ubuntu-gnome-terminal>
/etc/apparmor.d/abstractions/ubuntu-console-email:# Users of this abstraction need to include the ubuntu-helpers abstraction
/etc/apparmor.d/abstractions/ubuntu-console-email:#   include <abstractions/ubuntu-helpers>
/etc/apparmor.d/abstractions/ubuntu-console-email:  include if exists <abstractions/ubuntu-console-email.d>
/etc/apparmor.d/abstractions/xdg-open:#   # needed for ubuntu-* abstractions
/etc/apparmor.d/abstractions/xdg-open:#   include <abstractions/ubuntu-helpers>
/etc/apparmor.d/abstractions/xdg-open:#   include <abstractions/ubuntu-browsers>
/etc/apparmor.d/abstractions/xdg-open:#   include <abstractions/ubuntu-email>
/etc/apparmor.d/abstractions/kde:/usr/share/kubuntu-default-settings/kf5-settings/* r,
/etc/apparmor.d/abstractions/kde-open5:#   # needed for ubuntu-* abstractions
/etc/apparmor.d/abstractions/kde-open5:#   include <abstractions/ubuntu-helpers>
/etc/apparmor.d/abstractions/kde-open5:#   include <abstractions/ubuntu-browsers>
/etc/apparmor.d/abstractions/kde-open5:#   include <abstractions/ubuntu-email>
/etc/apparmor.d/abstractions/kde-open5:  # see: https://lists.ubuntu.com/archives/apparmor/2019-January/011925.html
/etc/apparmor.d/usr.bin.evince:  #include <abstractions/ubuntu-browsers>
/etc/apparmor.d/usr.bin.evince:  #include <abstractions/ubuntu-console-browsers>
/etc/apparmor.d/usr.bin.evince:  #include <abstractions/ubuntu-email>
/etc/apparmor.d/usr.bin.evince:  #include <abstractions/ubuntu-console-email>
/etc/apparmor.d/usr.bin.evince:  #include <abstractions/ubuntu-media-players>
/etc/apparmor.d/usr.bin.evince:  #include <abstractions/ubuntu-gnome-terminal>
/etc/apparmor.d/usr.bin.evince:  ##include <abstractions/ubuntu-xterm>
/etc/apparmor.d/usr.bin.evince:  ##include <abstractions/ubuntu-konsole>
/etc/apparmor.d/usr.bin.evince:  # For Xubuntu to launch the browser
/etc/apparmor.d/usr.bin.evince:  #include <abstractions/ubuntu-browsers>
/etc/apparmor.d/usr.bin.evince:  #include <abstractions/ubuntu-console-browsers>
/etc/apparmor.d/usr.bin.evince:  #include <abstractions/ubuntu-email>
/etc/apparmor.d/usr.bin.evince:  #include <abstractions/ubuntu-console-email>
/etc/apparmor.d/usr.bin.evince:  #include <abstractions/ubuntu-media-players>
/etc/apparmor.d/usr.bin.evince:  #include <abstractions/ubuntu-gnome-terminal>
/etc/apparmor.d/usr.bin.evince:  ##include <abstractions/ubuntu-xterm>
/etc/apparmor.d/usr.sbin.cupsd:# Author: Martin Pitt <martin.pitt@ubuntu.com>
grep: /etc/shadow-: Permission denied
/etc/rc1.d/K01whoopsie:DAEMON=/bin/sh -c 'export CRASH_DB_URL=https://daisy.ubuntu.com; exec whoopsie -f'
grep: /etc/ppp/chap-secrets: Permission denied
grep: /etc/ppp/pap-secrets: Permission denied
/etc/speech-dispatcher/speechd.conf:# Copyright (C) 2014-2016 Luke Yelavich <themuso@ubuntu.com>
/etc/speech-dispatcher/modules/espeak-ng-mbrola-generic.conf:# Copyright (C) 2014 Luke Yelavich <themuso@ubuntu.com>
/etc/speech-dispatcher/modules/espeak-mbrola-generic.conf:# Copyright (C) 2014 Luke Yelavich <themuso@ubuntu.com>
grep: /etc/ssl/private: Permission denied
/etc/grub.d/10_linux:ubuntu_recovery="1"
/etc/grub.d/10_linux:    Ubuntu|Kubuntu)
/etc/grub.d/10_linux:if [ "$ubuntu_recovery" = 1 ]; then
/etc/grub.d/10_linux:  if ([ "$ubuntu_recovery" = 0 ] || [ x$type != xrecovery ]) && \
/etc/grub.d/10_linux_zfs:ubuntu_recovery="1"
/etc/grub.d/10_linux_zfs:        # on ubuntu, loaded by the shim.
/etc/grub.d/10_linux_zfs:    last_booted_kernel=$(zfs get -H com.ubuntu.zsys:last-booted-kernel "${dataset}" | awk -v FS='\t' '{print $3}')
/etc/grub.d/10_linux_zfs:            last_used=$(zfs get -H com.ubuntu.zsys:last-used "${dataset}" | awk '{print $3}')
/etc/grub.d/10_linux_zfs:    is_zsys=$(zfs get -H com.ubuntu.zsys:bootfs "${base_dataset}" | awk '{print $3}')
/etc/grub.d/10_linux_zfs:    if ([ "${ubuntu_recovery}" = 0 ] || [ "${type}" != "recovery" ]) && \
/etc/grub.d/10_linux_zfs:            Ubuntu|Kubuntu)
/etc/grub.d/10_linux_zfs:    if [ "${ubuntu_recovery}" = 1 ]; then
/etc/grub.d/10_linux_zfs:	# $1: root dataset (eg rpool/ROOT/ubuntu_2zhm07@autozsys_k56fr6)
/etc/grub.d/10_linux_zfs:	# $3: initrd (eg /BOOT/ubuntu_2zhm07@autozsys_k56fr6/initrd.img-5.4.0-21-generic)
/etc/grub.d/10_linux_zfs:	# $4: kernel (eg /BOOT/ubuntu_2zhm07@autozsys_k56fr6/vmlinuz-5.4.0-21-generic)
/etc/grub.d/05_debian_theme:		Tanglu|Ubuntu|Kubuntu)
/etc/grub.d/05_debian_theme:	Ubuntu|Kubuntu)
grep: /etc/gshadow: Permission denied
/etc/init.d/whoopsie:DAEMON=/bin/sh -c 'export CRASH_DB_URL=https://daisy.ubuntu.com; exec whoopsie -f'
/etc/init.d/apparmor:#  Kees Cook <kees@ubuntu.com>
/etc/init.d/acpid:        MODULES="$(sed -rn 's#^(/lib/modules/[^/]+/)?kernel/(drivers|ubuntu)/acpi/([^/]+/)*(.*)\.ko:.*#\4#p' "/lib/modules/$(uname -r)/modules.dep")"
/etc/rcS.d/S01apparmor:#  Kees Cook <kees@ubuntu.com>
/etc/rc2.d/S01acpid:        MODULES="$(sed -rn 's#^(/lib/modules/[^/]+/)?kernel/(drivers|ubuntu)/acpi/([^/]+/)*(.*)\.ko:.*#\4#p' "/lib/modules/$(uname -r)/modules.dep")"
/etc/rc2.d/S01whoopsie:DAEMON=/bin/sh -c 'export CRASH_DB_URL=https://daisy.ubuntu.com; exec whoopsie -f'
/etc/init/whoopsie.conf:env CRASH_DB_URL=https://daisy.ubuntu.com
/etc/apport/crashdb.conf:default = 'ubuntu'
/etc/apport/crashdb.conf:        dcd = open('/var/lib/ubuntu_dist_channel').read()
/etc/apport/crashdb.conf:    'ubuntu': {
/etc/apport/crashdb.conf:        'bug_pattern_url': 'http://people.canonical.com/~ubuntu-archive/bugpatterns/bugpatterns.xml',
/etc/apport/crashdb.conf:        'dupdb_url': 'http://people.canonical.com/~ubuntu-archive/apport-duplicates',
/etc/apport/crashdb.conf:        'distro': 'ubuntu',
/etc/apport/crashdb.conf:        'bug_pattern_url': 'http://people.canonical.com/~ubuntu-archive/bugpatterns/bugpatterns.xml',
/etc/apport/native-origins.d/thunderbird:LP-PPA-ubuntu-mozilla-daily
/etc/apport/native-origins.d/thunderbird:LP-PPA-ubuntu-mozilla-daily-thunderbird-aurora
grep: /etc/security/opasswd: Permission denied
grep: /etc/sudoers: Permission denied
/etc/u-d-c-nvidia-runtimepm-override:# File created by ubuntu-drivers
/etc/rc3.d/S01acpid:        MODULES="$(sed -rn 's#^(/lib/modules/[^/]+/)?kernel/(drivers|ubuntu)/acpi/([^/]+/)*(.*)\.ko:.*#\4#p' "/lib/modules/$(uname -r)/modules.dep")"
/etc/rc3.d/S01whoopsie:DAEMON=/bin/sh -c 'export CRASH_DB_URL=https://daisy.ubuntu.com; exec whoopsie -f'
/etc/bash_completion.d/apport_completion:# apport-bug ubuntu-bug completion
/etc/bash_completion.d/apport_completion:    ubuntu-bug | apport-bug)
/etc/bash_completion.d/apport_completion:complete -F _apport-bug -o filenames -o dirnames ubuntu-bug
/etc/PackageKit/Vendor.conf:DefaultUrl=https://help.ubuntu.com/community/Repositories/
/etc/dbus-1/system.d/com.ubuntu.LanguageSelector.conf:                <allow own="com.ubuntu.LanguageSelector"/>
/etc/dbus-1/system.d/com.ubuntu.LanguageSelector.conf:		<allow send_destination="com.ubuntu.LanguageSelector"
/etc/dbus-1/system.d/com.ubuntu.LanguageSelector.conf:		       send_interface="com.ubuntu.LanguageSelector"/>
/etc/dbus-1/system.d/com.ubuntu.LanguageSelector.conf:		<allow receive_interface="com.ubuntu.LanguageSelector"
/etc/dbus-1/system.d/com.ubuntu.LanguageSelector.conf:   		       receive_sender="com.ubuntu.LanguageSelector"/>
/etc/dbus-1/system.d/com.ubuntu.LanguageSelector.conf:		<allow send_destination="com.ubuntu.LanguageSelector"
/etc/dbus-1/system.d/com.ubuntu.LanguageSelector.conf:		<allow send_destination="com.ubuntu.LanguageSelector"
/etc/dbus-1/system.d/com.ubuntu.WhoopsiePreferences.conf:    <allow own="com.ubuntu.WhoopsiePreferences"/>
/etc/dbus-1/system.d/com.ubuntu.WhoopsiePreferences.conf:    <allow send_destination="com.ubuntu.WhoopsiePreferences" 
/etc/dbus-1/system.d/com.ubuntu.WhoopsiePreferences.conf:           send_interface="com.ubuntu.WhoopsiePreferences"/>
/etc/dbus-1/system.d/com.ubuntu.WhoopsiePreferences.conf:    <allow send_destination="com.ubuntu.WhoopsiePreferences" 
/etc/dbus-1/system.d/com.ubuntu.WhoopsiePreferences.conf:    <allow send_destination="com.ubuntu.WhoopsiePreferences" 
/etc/dbus-1/system.d/com.ubuntu.SoftwareProperties.conf:    <allow own="com.ubuntu.SoftwareProperties"/>
/etc/dbus-1/system.d/com.ubuntu.SoftwareProperties.conf:    <allow send_destination="com.ubuntu.SoftwareProperties"
/etc/dbus-1/system.d/com.ubuntu.SoftwareProperties.conf:           send_interface="com.ubuntu.SoftwareProperties"/>
/etc/dbus-1/system.d/com.ubuntu.SoftwareProperties.conf:    <allow send_destination="com.ubuntu.SoftwareProperties"
/etc/dbus-1/system.d/com.ubuntu.SoftwareProperties.conf:    <allow send_destination="com.ubuntu.DeviceDriver"
/etc/dbus-1/system.d/com.ubuntu.USBCreator.conf:    <allow own="com.ubuntu.USBCreator"/>
/etc/dbus-1/system.d/com.ubuntu.USBCreator.conf:    <allow send_destination="com.ubuntu.USBCreator" 
/etc/dbus-1/system.d/com.ubuntu.USBCreator.conf:           send_interface="com.ubuntu.USBCreator"/>
/etc/dbus-1/system.d/com.ubuntu.USBCreator.conf:    <allow send_destination="com.ubuntu.USBCreator" 
/etc/dbus-1/system.d/com.ubuntu.USBCreator.conf:    <allow send_destination="com.ubuntu.USBCreator" 
/etc/rc4.d/S01acpid:        MODULES="$(sed -rn 's#^(/lib/modules/[^/]+/)?kernel/(drivers|ubuntu)/acpi/([^/]+/)*(.*)\.ko:.*#\4#p' "/lib/modules/$(uname -r)/modules.dep")"
/etc/rc4.d/S01whoopsie:DAEMON=/bin/sh -c 'export CRASH_DB_URL=https://daisy.ubuntu.com; exec whoopsie -f'
/etc/xdg/autostart/ubuntu-advantage-notification.desktop:Exec=/usr/lib/update-notifier/ubuntu-advantage-notification
/etc/xdg/autostart/ubuntu-report-on-upgrade.desktop:Exec=/usr/bin/ubuntu-report send upgrade
/etc/xdg/systemd/user/default.target.wants/ubuntu-report.path:PathExists=%h/.cache/ubuntu-report/pending
grep: /etc/apt/trusted.gpg.d/ubuntu-keyring-2012-cdimage.gpg: binary file matches
grep: /etc/apt/trusted.gpg.d/ubuntu-keyring-2018-archive.gpg: binary file matches
/etc/apt/sources.list:# See http://help.ubuntu.com/community/UpgradeNotes for how to upgrade to
/etc/apt/sources.list:deb http://in.archive.ubuntu.com/ubuntu/ jammy main restricted
/etc/apt/sources.list:# deb-src http://in.archive.ubuntu.com/ubuntu/ jammy main restricted
/etc/apt/sources.list:# deb-src http://in.archive.ubuntu.com/ubuntu/ jammy-updates main restricted
/etc/apt/sources.list:deb http://in.archive.ubuntu.com/ubuntu/ jammy universe
/etc/apt/sources.list:# deb-src http://in.archive.ubuntu.com/ubuntu/ jammy universe
/etc/apt/sources.list:# deb-src http://in.archive.ubuntu.com/ubuntu/ jammy-updates universe
/etc/apt/sources.list:deb http://in.archive.ubuntu.com/ubuntu/ jammy multiverse
/etc/apt/sources.list:# deb-src http://in.archive.ubuntu.com/ubuntu/ jammy multiverse
/etc/apt/sources.list:# deb-src http://in.archive.ubuntu.com/ubuntu/ jammy-updates multiverse
/etc/apt/sources.list:# deb-src http://in.archive.ubuntu.com/ubuntu/ jammy-backports main restricted universe multiverse
/etc/apt/sources.list:deb http://security.ubuntu.com/ubuntu jammy-security main restricted
/etc/apt/sources.list:# deb-src http://security.ubuntu.com/ubuntu jammy-security main restricted
/etc/apt/sources.list:deb http://security.ubuntu.com/ubuntu jammy-security universe
/etc/apt/sources.list:# deb-src http://security.ubuntu.com/ubuntu jammy-security universe
/etc/apt/sources.list:deb http://security.ubuntu.com/ubuntu jammy-security multiverse
/etc/apt/sources.list:# deb-src http://security.ubuntu.com/ubuntu jammy-security multiverse
/etc/apt/apt.conf.d/20apt-esm-hook.conf:	"[ ! -f /usr/lib/ubuntu-advantage/apt-esm-json-hook ] || /usr/lib/ubuntu-advantage/apt-esm-json-hook || true";
/etc/apt/sources.list.save:# See http://help.ubuntu.com/community/UpgradeNotes for how to upgrade to
/etc/apt/sources.list.save:deb http://in.archive.ubuntu.com/ubuntu/ jammy main restricted
/etc/apt/sources.list.save:# deb-src http://in.archive.ubuntu.com/ubuntu/ jammy main restricted
/etc/apt/sources.list.save:# deb-src http://in.archive.ubuntu.com/ubuntu/ jammy-updates main restricted
/etc/apt/sources.list.save:deb http://in.archive.ubuntu.com/ubuntu/ jammy universe
/etc/apt/sources.list.save:# deb-src http://in.archive.ubuntu.com/ubuntu/ jammy universe
/etc/apt/sources.list.save:# deb-src http://in.archive.ubuntu.com/ubuntu/ jammy-updates universe
/etc/apt/sources.list.save:deb http://in.archive.ubuntu.com/ubuntu/ jammy multiverse
/etc/apt/sources.list.save:# deb-src http://in.archive.ubuntu.com/ubuntu/ jammy multiverse
/etc/apt/sources.list.save:# deb-src http://in.archive.ubuntu.com/ubuntu/ jammy-updates multiverse
/etc/apt/sources.list.save:# deb-src http://in.archive.ubuntu.com/ubuntu/ jammy-backports main restricted universe multiverse
/etc/apt/sources.list.save:deb http://security.ubuntu.com/ubuntu jammy-security main restricted
/etc/apt/sources.list.save:# deb-src http://security.ubuntu.com/ubuntu jammy-security main restricted
/etc/apt/sources.list.save:deb http://security.ubuntu.com/ubuntu jammy-security universe
/etc/apt/sources.list.save:# deb-src http://security.ubuntu.com/ubuntu jammy-security universe
/etc/apt/sources.list.save:deb http://security.ubuntu.com/ubuntu jammy-security multiverse
/etc/apt/sources.list.save:# deb-src http://security.ubuntu.com/ubuntu jammy-security multiverse
/etc/update-motd.d/91-contract-ua-esm-status:contract_status_stamp="/var/lib/ubuntu-advantage/messages/motd-contract-status"
/etc/update-motd.d/91-contract-ua-esm-status:auto_attach_stamp="/var/lib/ubuntu-advantage/messages/motd-auto-attach-status"
/etc/update-motd.d/91-release-upgrade:if [ -x /usr/lib/ubuntu-release-upgrader/release-upgrade-motd ]; then
/etc/update-motd.d/91-release-upgrade:    exec /usr/lib/ubuntu-release-upgrader/release-upgrade-motd
/etc/update-motd.d/10-help-text:printf " * Documentation:  https://help.ubuntu.com\n"
/etc/update-motd.d/10-help-text:printf " * Support:        https://ubuntu.com/advantage\n"
/etc/update-motd.d/50-motd-news:[ -n "$URLS" ] || URLS="https://motd.ubuntu.com"
/etc/update-motd.d/50-motd-news:		https://motd.ubuntu.com)
/etc/logrotate.d/ubuntu-advantage-tools:# of /var/log/ubuntu-advantage*.log files.
/etc/logrotate.d/ubuntu-advantage-tools:/var/log/ubuntu-advantage*.log {
/etc/sysctl.d/10-ptrace.conf:# https://wiki.ubuntu.com/SecurityTeam/Roadmap/KernelHardening#ptrace
grep: /etc/polkit-1/localauthority: Permission denied
/etc/update-manager/meta-release:URI = https://changelogs.ubuntu.com/meta-release
/etc/update-manager/meta-release:URI_LTS = https://changelogs.ubuntu.com/meta-release-lts
/etc/update-manager/release-upgrades.d/ubuntu-advantage-upgrades.cfg:PostInstallScripts=./xorg_fix_proprietary.py, /usr/lib/ubuntu-advantage/upgrade_lts_contract.py
grep: /etc/sudoers.d/README: Permission denied
grep: /etc/NetworkManager/system-connections/Venkatanathan A16.nmconnection: Permission denied
grep: /etc/NetworkManager/system-connections/SEC EEE 5F WIFI.nmconnection: Permission denied
grep: /etc/NetworkManager/system-connections/Airtel_1975.nmconnection: Permission denied
grep: /etc/NetworkManager/system-connections/Test.nmconnection: Permission denied
grep: /etc/ld.so.cache: binary file matches
grep: /etc/ufw/before.init: Permission denied
grep: /etc/ufw/before.rules: Permission denied
grep: /etc/ufw/before6.rules: Permission denied
grep: /etc/ufw/after.init: Permission denied
grep: /etc/ufw/user6.rules: Permission denied
grep: /etc/ufw/after6.rules: Permission denied
grep: /etc/ufw/after.rules: Permission denied
grep: /etc/ufw/user.rules: Permission denied
grep: /etc/shadow: Permission denied
grep: /etc/pulse/client.conf.d/01-enable-autospawn.conf: No such file or directory
/etc/depmod.d/ubuntu.conf:search updates ubuntu built-in
grep: /etc/brlapi.key: Permission denied
/etc/udev/rules.d/70-snap.snap-store.rules:KERNEL=="dma_buf_te", TAG+="snap_snap-store_ubuntu-software"
/etc/udev/rules.d/70-snap.snap-store.rules:KERNEL=="galcore", TAG+="snap_snap-store_ubuntu-software"
/etc/udev/rules.d/70-snap.snap-store.rules:KERNEL=="mali[0-9]*", TAG+="snap_snap-store_ubuntu-software"
/etc/udev/rules.d/70-snap.snap-store.rules:KERNEL=="nvhost-*", TAG+="snap_snap-store_ubuntu-software"
/etc/udev/rules.d/70-snap.snap-store.rules:KERNEL=="nvmap", TAG+="snap_snap-store_ubuntu-software"
/etc/udev/rules.d/70-snap.snap-store.rules:KERNEL=="pvr_sync", TAG+="snap_snap-store_ubuntu-software"
/etc/udev/rules.d/70-snap.snap-store.rules:KERNEL=="renderD[0-9]*", TAG+="snap_snap-store_ubuntu-software"
/etc/udev/rules.d/70-snap.snap-store.rules:KERNEL=="tegra_dc_[0-9]*", TAG+="snap_snap-store_ubuntu-software"
/etc/udev/rules.d/70-snap.snap-store.rules:KERNEL=="tegra_dc_ctrl", TAG+="snap_snap-store_ubuntu-software"
/etc/udev/rules.d/70-snap.snap-store.rules:KERNEL=="vchiq", TAG+="snap_snap-store_ubuntu-software"
/etc/udev/rules.d/70-snap.snap-store.rules:KERNEL=="vcsm-cma", TAG+="snap_snap-store_ubuntu-software"
/etc/udev/rules.d/70-snap.snap-store.rules:SUBSYSTEM=="dma_heap", KERNEL=="linux,cma", TAG+="snap_snap-store_ubuntu-software"
/etc/udev/rules.d/70-snap.snap-store.rules:SUBSYSTEM=="dma_heap", KERNEL=="system", TAG+="snap_snap-store_ubuntu-software"
/etc/udev/rules.d/70-snap.snap-store.rules:SUBSYSTEM=="drm", KERNEL=="card[0-9]*", TAG+="snap_snap-store_ubuntu-software"
/etc/udev/rules.d/70-snap.snap-store.rules:TAG=="snap_snap-store_ubuntu-software", SUBSYSTEM!="module", SUBSYSTEM!="subsystem", RUN+="/usr/lib/snapd/snap-device-helper $env{ACTION} snap_snap-store_ubuntu-software $devpath $major:$minor"
/etc/udev/rules.d/70-snap.snap-store.rules:KERNEL=="dma_buf_te", TAG+="snap_snap-store_ubuntu-software-local-file"
/etc/udev/rules.d/70-snap.snap-store.rules:KERNEL=="galcore", TAG+="snap_snap-store_ubuntu-software-local-file"
/etc/udev/rules.d/70-snap.snap-store.rules:KERNEL=="mali[0-9]*", TAG+="snap_snap-store_ubuntu-software-local-file"
/etc/udev/rules.d/70-snap.snap-store.rules:KERNEL=="nvhost-*", TAG+="snap_snap-store_ubuntu-software-local-file"
/etc/udev/rules.d/70-snap.snap-store.rules:KERNEL=="nvmap", TAG+="snap_snap-store_ubuntu-software-local-file"
/etc/udev/rules.d/70-snap.snap-store.rules:KERNEL=="pvr_sync", TAG+="snap_snap-store_ubuntu-software-local-file"
/etc/udev/rules.d/70-snap.snap-store.rules:KERNEL=="renderD[0-9]*", TAG+="snap_snap-store_ubuntu-software-local-file"
/etc/udev/rules.d/70-snap.snap-store.rules:KERNEL=="tegra_dc_[0-9]*", TAG+="snap_snap-store_ubuntu-software-local-file"
/etc/udev/rules.d/70-snap.snap-store.rules:KERNEL=="tegra_dc_ctrl", TAG+="snap_snap-store_ubuntu-software-local-file"
/etc/udev/rules.d/70-snap.snap-store.rules:KERNEL=="vchiq", TAG+="snap_snap-store_ubuntu-software-local-file"
/etc/udev/rules.d/70-snap.snap-store.rules:KERNEL=="vcsm-cma", TAG+="snap_snap-store_ubuntu-software-local-file"
/etc/udev/rules.d/70-snap.snap-store.rules:SUBSYSTEM=="dma_heap", KERNEL=="linux,cma", TAG+="snap_snap-store_ubuntu-software-local-file"
/etc/udev/rules.d/70-snap.snap-store.rules:SUBSYSTEM=="dma_heap", KERNEL=="system", TAG+="snap_snap-store_ubuntu-software-local-file"
/etc/udev/rules.d/70-snap.snap-store.rules:SUBSYSTEM=="drm", KERNEL=="card[0-9]*", TAG+="snap_snap-store_ubuntu-software-local-file"
/etc/udev/rules.d/70-snap.snap-store.rules:TAG=="snap_snap-store_ubuntu-software-local-file", SUBSYSTEM!="module", SUBSYSTEM!="subsystem", RUN+="/usr/lib/snapd/snap-device-helper $env{ACTION} snap_snap-store_ubuntu-software-local-file $devpath $major:$minor"
/etc/appstream.conf:[ubuntu]
/etc/appstream.conf:ScreenshotUrl=http://screenshots.ubuntu.com
/etc/ubuntu-advantage/help_data.yaml:      https://ubuntu.com/security/certifications/docs/usg
/etc/ubuntu-advantage/help_data.yaml:      https://ubuntu.com/security/esm
/etc/ubuntu-advantage/help_data.yaml:     the service at https://ubuntu.com/security/esm
/etc/ubuntu-advantage/help_data.yaml:      https://ubuntu.com/security/certifications#fips
/etc/ubuntu-advantage/help_data.yaml:      You can find out more at https://ubuntu.com/security/certifications#fips.
/etc/ubuntu-advantage/help_data.yaml:      https://ubuntu.com/security/livepatch
/etc/ubuntu-advantage/help_data.yaml:    ROS ESM service at https://ubuntu.com/robotics/ros-esm
/etc/ubuntu-advantage/help_data.yaml:    https://ubuntu.com/robotics/ros-esm
/etc/gdm3/config-error-dialog.sh:# Author: Gunnar Hjalmarsson <gunnarhj@ubuntu.com>
/etc/gnome/defaults.list:application/vnd.debian.binary-package=snap-store_ubuntu-software-local-file.desktop
/etc/gnome/defaults.list:application/vnd.ms-cab-compressed=snap-store_ubuntu-software-local-file.desktop
/etc/gnome/defaults.list:application/x-cab=snap-store_ubuntu-software-local-file.desktop
/etc/gnome/defaults.list:application/x-ms-cab-compressed=snap-store_ubuntu-software-local-file.desktop
/etc/gnome/defaults.list:application/x-deb=snap-store_ubuntu-software-local-file.desktop
/etc/gnome/defaults.list:application/x-debian-package=snap-store_ubuntu-software-local-file.desktop
/etc/gnome/defaults.list:text/x-c++hdr=ubuntusdk.desktop
/etc/gnome/defaults.list:text/x-c++src=ubuntusdk.desktop
/etc/gnome/defaults.list:text/x-xsrc=ubuntusdk.desktop
/etc/gnome/defaults.list:x-scheme-handler/snap=snap-store_ubuntu-software.desktop
grep: /etc/cups/ssl: Permission denied
grep: /etc/cups/subscriptions.conf.O: Permission denied
grep: /etc/cups/printers.conf.O: Permission denied
grep: /etc/cups/printers.conf: Permission denied
grep: /etc/cups/subscriptions.conf: Permission denied
grep: /etc/.pwd.lock: Permission denied
/etc/os-release:ID=ubuntu
/etc/os-release:HOME_URL="https://www.ubuntu.com/"
/etc/os-release:SUPPORT_URL="https://help.ubuntu.com/"
/etc/os-release:BUG_REPORT_URL="https://bugs.launchpad.net/ubuntu/"
/etc/os-release:PRIVACY_POLICY_URL="https://www.ubuntu.com/legal/terms-and-policies/privacy-policy"
/etc/dpkg/origins/ubuntu:Vendor-URL: http://www.ubuntu.com/
/etc/dpkg/origins/ubuntu:Bugs: https://bugs.launchpad.net/ubuntu/+filebug
/etc/dpkg/origins/default:Vendor-URL: http://www.ubuntu.com/
/etc/dpkg/origins/default:Bugs: https://bugs.launchpad.net/ubuntu/+filebug
/etc/rc5.d/S01acpid:        MODULES="$(sed -rn 's#^(/lib/modules/[^/]+/)?kernel/(drivers|ubuntu)/acpi/([^/]+/)*(.*)\.ko:.*#\4#p' "/lib/modules/$(uname -r)/modules.dep")"
/etc/rc5.d/S01whoopsie:DAEMON=/bin/sh -c 'export CRASH_DB_URL=https://daisy.ubuntu.com; exec whoopsie -f'
/etc/systemd/system/timers.target.wants/ua-timer.timer:ConditionPathExists=/var/lib/ubuntu-advantage/private/machine-token.json
/etc/systemd/system/multi-user.target.wants/ua-reboot-cmds.service:ConditionPathExists=/var/lib/ubuntu-advantage/marker-reboot-cmds-required
/etc/systemd/system/multi-user.target.wants/ua-reboot-cmds.service:ConditionPathExists=/var/lib/ubuntu-advantage/private/machine-token.json
/etc/systemd/system/multi-user.target.wants/ua-reboot-cmds.service:ExecStart=/usr/bin/python3 /usr/lib/ubuntu-advantage/reboot_cmds.py
/etc/systemd/system/multi-user.target.wants/ubuntu-advantage.service:# sudo systemctl stop ubuntu-advantage.service
/etc/systemd/system/multi-user.target.wants/ubuntu-advantage.service:# sudo systemctl disable ubuntu-advantage.service
/etc/systemd/system/multi-user.target.wants/ubuntu-advantage.service:Documentation=man:ubuntu-advantage https://ubuntu.com/advantage
/etc/systemd/system/multi-user.target.wants/ubuntu-advantage.service:After=network.target network-online.target systemd-networkd.service ua-auto-attach.service cloud-config.service ubuntu-advantage-cloud-id-shim.service
/etc/systemd/system/multi-user.target.wants/ubuntu-advantage.service:ConditionPathExists=!/var/lib/ubuntu-advantage/private/machine-token.json
/etc/systemd/system/multi-user.target.wants/ubuntu-advantage.service:ConditionPathExists=|/run/ubuntu-advantage/flags/auto-attach-failed
/etc/systemd/system/multi-user.target.wants/ubuntu-advantage.service:ExecStart=/usr/bin/python3 /usr/lib/ubuntu-advantage/daemon.py
/etc/systemd/system/multi-user.target.wants/ubuntu-advantage.service:WorkingDirectory=/var/lib/ubuntu-advantage/
/etc/systemd/user/default.target.wants/ubuntu-report.path:PathExists=%h/.cache/ubuntu-report/pending
/etc/systemd/timesyncd.conf:#FallbackNTP=ntp.ubuntu.com
/etc/profile.d/cedilla-portuguese.sh:# Author: Gunnar Hjalmarsson <gunnarhj@ubuntu.com>
grep: /etc/profile.d/debuginfod.sh: Permission denied
grep: /etc/profile.d/debuginfod.csh: Permission denied
grep: /etc/gshadow-: Permission denied
grep: /etc/alternatives/cpp: binary file matches
grep: /etc/alternatives/rsh: binary file matches
grep: /etc/alternatives/rlogin: binary file matches
grep: /etc/alternatives/shimx64.efi.signed: binary file matches
/etc/alternatives/open:         LXDE|Lubuntu)
grep: /etc/alternatives/netcat: binary file matches
/etc/alternatives/text.plymouth:Description=Text mode theme based on ubuntu-logo theme
/etc/alternatives/text.plymouth:ModuleName=ubuntu-text
/etc/alternatives/text.plymouth:[ubuntu-text]
grep: /etc/alternatives/gdm-theme.gresource: binary file matches
grep: /etc/alternatives/nc: binary file matches
```

grep -w -n world newfile 

## OUTPUT

```
1:Hello world
2:hello world
3:Linux is world number 1
```

cat < newfile 
```
Hello world
hello world
Linux is world number 1
Unix is predecessor
Linux is best in this World
^d
```

cat > newfile
```
Hello world
hello world
Linux is world number 1
Unix is predecessor
Linux is best in this World
^d
 ```
egrep -w 'Hello|hello' newfile 

## OUTPUT
```
Hello world
hello world
```

egrep -w '(H|h)ello' newfile 

## OUTPUT

```
Hello world
hello world
```

egrep -w '(H|h)ell[a-z]' newfile 

## OUTPUT
```
Hello world
hello world
```

egrep '(^hello)' newfile 

## OUTPUT
```
hello world
```

egrep '(world$)' newfile 

## OUTPUT
```
Hello world
hello world
```

egrep '(World$)' newfile 

## OUTPUT
```
Linux is best in this World
```

egrep '((W|w)orld$)' newfile 

## OUTPUT
```
Hello world
hello world
Linux is best in this World
```

egrep '[1-9]' newfile 

## OUTPUT
```
Linux is world number 1
```

egrep 'Linux.*world' newfile 

## OUTPUT
```
Linux is world number 1
```

egrep 'Linux.*World' newfile 

## OUTPUT
```
Linux is best in this World
```

egrep l{2} newfile

## OUTPUT
```
Hello world
hello world
```

egrep 's{1,2}' newfile

## OUTPUT 
```
Linux is world number 1
Unix is predecessor
Linux is best in this World
```

cat > file23
```
1001 | Ram | 10000 | HR
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
1003 | Joe |  7000 | Developer
1001 | Ram | 10000 | HR
^d
```

sed -n -e '3p' file23

## OUTPUT
```
1002 | tom |  5000 | Admin
```

sed -n -e '$p' file23

## OUTPUT
```
1001 | Ram | 10000 | HR
```

sed  -e 's/Ram/Sita/' file23

## OUTPUT
```
1001 | Sita | 10000 | HR
1001 | Sita | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
1003 | Joe |  7000 | Developer
1001 | Sita | 10000 | HR
```

sed  -e '2s/Ram/Sita/' file23

## OUTPUT
```
1001 | Ram | 10000 | HR
1001 | Sita | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
1003 | Joe |  7000 | Developer
1001 | Ram | 10000 | HR
```

sed  '/tom/s/5000/6000/' file23

## OUTPUT
```
1001 | Ram | 10000 | HR
1001 | Ram | 10000 | HR
1002 | tom |  6000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
1003 | Joe |  7000 | Developer
1001 | Ram | 10000 | HR
```

sed -n -e '1,5p' file23

## OUTPUT
```
1001 | Ram | 10000 | HR
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
```

sed -n -e '2,/Joe/p' file23

## OUTPUT
```
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
```

sed -n -e '/tom/,/Joe/p' file23

## OUTPUT
```
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
```

seq 10 

## OUTPUT
```
1
2
3
4
5
6
7
8
9
10
```

seq 10 | sed -n '4,6p'

## OUTPUT
```
4
5
6
```

seq 10 | sed -n '2,~4p'

## OUTPUT
```
2
3
4
```

seq 3 | sed '2a hello'

## OUTPUT
```
1
2
hello
3
```

seq 2 | sed '2i hello'

## OUTPUT
```
1
hello
2
```

seq 10 | sed '2,9c hello'

## OUTPUT
```
1
hello
10
```

sed -n '2,4{s/^/$/;p}' file23

## OUTPUT
```
$1001 | Ram | 10000 | HR
$1002 | tom |  5000 | Admin
$1003 | Joe |  7000 | Developer
```

sed -n '2,4{s/$/*/;p}' file23
```
1001 | Ram | 10000 | HR*
1002 | tom |  5000 | Admin*
1003 | Joe |  7000 | Developer*
```

#Sorting File content

cat > file21
```
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
``` 
sort file21

## OUTPUT
```
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1004 | Sit |  7000 | Dev
1005 | Sam |  5000 | HR
```

cat > file22
```
1001 | Ram | 10000 | HR
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
``` 
uniq file22

## OUTPUT
```
1001 | Ram | 10000 | HR
1002 | tom |  5000 | Admin
1003 | Joe |  7000 | Developer
1005 | Sam |  5000 | HR
1004 | Sit |  7000 | Dev
```

#Using tr command

cat file23 | tr [:lower:] [:upper:]

## OUTPUT
```
1001 | RAM | 10000 | HR
1001 | RAM | 10000 | HR
1002 | TOM |  5000 | ADMIN
1003 | JOE |  7000 | DEVELOPER
1005 | SAM |  5000 | HR
1004 | SIT |  7000 | DEV
1003 | JOE |  7000 | DEVELOPER
1001 | RAM | 10000 | HR
```

cat < urllist.txt
```
www. yahoo. com
www. google. com
www. mrcet.... com
^d
 ```
cat > urllist.txt
```
www. yahoo. com
www. google. com
www. mrcet.... com
 ```
cat urllist.txt | tr -d ' '

## OUTPUT
```
www.yahoo.com
www.google.com
www.mrcet....com
```

cat urllist.txt | tr -d ' ' | tr -s '.'

## OUTPUT
```
www.yahoo.com
www.google.com
www.mrcet.com
```

#Backup commands

tar -cvf backup.tar *

## OUTPUT
```
argshift1.sh
argshift.sh
backupdir/
backupdir/newfile
backupdir/file21
backupdir/OS-Linux-commands-Shell-script/
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-17-30.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-12-39.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-35-33.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-32-26.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-04-03.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-49-33.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-05-03.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-13-35.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-36-48.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-56-15.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-19-45.png
backupdir/OS-Linux-commands-Shell-script/.git/
backupdir/OS-Linux-commands-Shell-script/.git/description
backupdir/OS-Linux-commands-Shell-script/.git/refs/
backupdir/OS-Linux-commands-Shell-script/.git/refs/tags/
backupdir/OS-Linux-commands-Shell-script/.git/refs/remotes/
backupdir/OS-Linux-commands-Shell-script/.git/refs/remotes/origin/
backupdir/OS-Linux-commands-Shell-script/.git/refs/remotes/origin/HEAD
backupdir/OS-Linux-commands-Shell-script/.git/refs/heads/
backupdir/OS-Linux-commands-Shell-script/.git/refs/heads/main
backupdir/OS-Linux-commands-Shell-script/.git/logs/
backupdir/OS-Linux-commands-Shell-script/.git/logs/refs/
backupdir/OS-Linux-commands-Shell-script/.git/logs/refs/remotes/
backupdir/OS-Linux-commands-Shell-script/.git/logs/refs/remotes/origin/
backupdir/OS-Linux-commands-Shell-script/.git/logs/refs/remotes/origin/HEAD
backupdir/OS-Linux-commands-Shell-script/.git/logs/refs/heads/
backupdir/OS-Linux-commands-Shell-script/.git/logs/refs/heads/main
backupdir/OS-Linux-commands-Shell-script/.git/logs/HEAD
backupdir/OS-Linux-commands-Shell-script/.git/packed-refs
backupdir/OS-Linux-commands-Shell-script/.git/info/
backupdir/OS-Linux-commands-Shell-script/.git/info/exclude
backupdir/OS-Linux-commands-Shell-script/.git/index
backupdir/OS-Linux-commands-Shell-script/.git/branches/
backupdir/OS-Linux-commands-Shell-script/.git/hooks/
backupdir/OS-Linux-commands-Shell-script/.git/hooks/update.sample
backupdir/OS-Linux-commands-Shell-script/.git/hooks/fsmonitor-watchman.sample
backupdir/OS-Linux-commands-Shell-script/.git/hooks/pre-rebase.sample
backupdir/OS-Linux-commands-Shell-script/.git/hooks/applypatch-msg.sample
backupdir/OS-Linux-commands-Shell-script/.git/hooks/commit-msg.sample
backupdir/OS-Linux-commands-Shell-script/.git/hooks/pre-push.sample
backupdir/OS-Linux-commands-Shell-script/.git/hooks/prepare-commit-msg.sample
backupdir/OS-Linux-commands-Shell-script/.git/hooks/pre-applypatch.sample
backupdir/OS-Linux-commands-Shell-script/.git/hooks/pre-commit.sample
backupdir/OS-Linux-commands-Shell-script/.git/hooks/pre-receive.sample
backupdir/OS-Linux-commands-Shell-script/.git/hooks/post-update.sample
s/heads/
backupdir/OS-Linux-commands-Shell-script/.git/logs/refs/heads/main
backupdir/OS-Linux-commands-Shell-script/.git/logs/HEAD
backupdir/OS-Linux-commands-Shell-script/.git/packed-refs
backupdir/OS-Linux-commands-Shell-script/.git/info/
backupdir/OS-Linux-commands-Shell-script/.git/info/exclude
backupdir/OS-Linux-commands-Shell-script/.git/index
backupdir/OS-Linux-commands-Shell-script/.git/branches/
backupdir/OS-Linux-commands-Shell-script/.git/hooks/
backupdir/OS-Linux-commands-Shell-script/.git/hooks/update.sample
backupdir/OS-Linux-commands-Shell-script/.git/hooks/fsmonitor-watchman.sample
backupdir/OS-Linux-commands-Shell-script/.git/hooks/pre-rebase.sample
backupdir/OS-Linux-commands-Shell-script/.git/hooks/applypatch-msg.sample
backupdir/OS-Linux-commands-Shell-script/.git/hooks/commit-msg.sample
backupdir/OS-Linux-commands-Shell-script/.git/hooks/pre-push.sample
backupdir/OS-Linux-commands-Shell-script/.git/hooks/prepare-commit-msg.sample
backupdir/OS-Linux-commands-Shell-script/.git/hooks/pre-applypatch.sample
backupdir/OS-Linux-commands-Shell-script/.git/hooks/pre-commit.sample
backupdir/OS-Linux-commands-Shell-script/.git/hooks/pre-receive.sample
backupdir/OS-Linux-commands-Shell-script/.git/hooks/post-update.sample
backupdir/OS-Linux-commands-Shell-script/.git/hooks/push-to-checkout.sample
backupdir/OS-Linux-commands-Shell-script/.git/hooks/pre-merge-commit.sample
backupdir/OS-Linux-commands-Shell-script/.git/HEAD
backupdir/OS-Linux-commands-Shell-script/.git/objects/
backupdir/OS-Linux-commands-Shell-script/.git/objects/info/
backupdir/OS-Linux-commands-Shell-script/.git/objects/pack/
backupdir/OS-Linux-commands-Shell-script/.git/objects/pack/pack-ec36fa2c38f0d702b12329b43a753a363ab5d761.idx
backupdir/OS-Linux-commands-Shell-script/.git/objects/pack/pack-ec36fa2c38f0d702b12329b43a753a363ab5d761.pack
backupdir/OS-Linux-commands-Shell-script/.git/config
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-58-09.png
backupdir/OS-Linux-commands-Shell-script/image.pngbackupdir/OS-Linux-commands-Shell-script/.git/hooks/push-to-checkout.sample
backupdir/OS-Linux-commands-Shell-script/.git/hooks/pre-merge-commit.sample
backupdir/OS-Linux-commands-Shell-script/.git/HEAD
backupdir/OS-Linux-commands-Shell-script/.git/objects/
backupdir/OS-Linux-commands-Shell-script/.git/objects/info/
backupdir/OS-Linux-commands-Shell-script/.git/objects/pack/
backupdir/OS-Linux-commands-Shell-script/.git/objects/pack/pack-ec36fa2c38f0d702b12329b43a753a363ab5d761.idx
backupdir/OS-Linux-commands-Shell-script/.git/objects/pack/pack-ec36fa2c38f0d702b12329b43a753a363ab5d761.pack
backupdir/OS-Linux-commands-Shell-script/.git/config
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-58-09.png
backupdir/OS-Linux-commands-Shell-script/image.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-34-40.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-57-42.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-36-38.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-19-42.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-58-36.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-35-44.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-08-11.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-00-06.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-32-59.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-43-26.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-07-10.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-29-22.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-14-46.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-36-06.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-38-17.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-59-05.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-16-47.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-38-33.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-58-59.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-55-15.png
backupdir/OS-Linux-commands-Shell-script/README.md
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-39-22.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-42-16.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-06-26.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-51-02.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-39-18.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-46-46.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-30-26.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-52-10.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-30-41.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-45-16.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-46-30.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-45-47.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-17-22.png
backupdir/OS-Linux-commands-Shell-script/LICENSE
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-09-30.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-41-07.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-23-44.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-57-52.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-11-09.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-47-19.png
backupdir/OS-Linux-commands-Shell-script/file1
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-15-24.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-41-04.png
backupdir/file22
backupdir/file23
backupdir/urllist.txt
backupdir/backup.tar
backupdir/file11
backupdir/file2
backupdir/file1
casecheck.sh
cities
data.dat
elifcheck.sh
exread1.sh
exread.sh
file1
file11
file2
file21
file22
file23
forbreak.sh
forctype.sh
forin1.sh
forin2.sh
forin3.sh
forinfile.sh
fornested1.sh
funcex.sh
herecheck.txt
ifcompound.sh
ifnested1.sh
ifnested.sh
iftest.sh
my-script.sh
nc.awk
newfile
one
OS-Linux-commands-Shell-script/
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 19-12-09.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-06-20.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-40-20.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-16-41.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-17-30.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-12-39.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-46-30-1.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-35-33.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 20-11-56.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-32-26.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-04-03.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-49-33.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 19-16-26.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 20-11-08.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 19-34-51.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-05-03.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-13-35.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-36-48.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 19-52-43.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-56-15.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-19-45.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 21-11-27.png
OS-Linux-commands-Shell-script/.git/
OS-Linux-commands-Shell-script/.git/description
OS-Linux-commands-Shell-script/.git/refs/
OS-Linux-commands-Shell-script/.git/refs/tags/
OS-Linux-commands-Shell-script/.git/refs/remotes/
OS-Linux-commands-Shell-script/.git/refs/remotes/origin/
OS-Linux-commands-Shell-script/.git/refs/remotes/origin/HEAD
OS-Linux-commands-Shell-script/.git/refs/heads/
OS-Linux-commands-Shell-script/.git/refs/heads/main
OS-Linux-commands-Shell-script/.git/logs/
OS-Linux-commands-Shell-script/.git/logs/refs/
OS-Linux-commands-Shell-script/.git/logs/refs/remotes/
OS-Linux-commands-Shell-script/.git/logs/refs/remotes/origin/
OS-Linux-commands-Shell-script/.git/logs/refs/remotes/origin/HEAD
OS-Linux-commands-Shell-script/.git/logs/refs/heads/
OS-Linux-commands-Shell-script/.git/logs/refs/heads/main
OS-Linux-commands-Shell-script/.git/logs/HEAD
OS-Linux-commands-Shell-script/.git/packed-refs
OS-Linux-commands-Shell-script/.git/info/
OS-Linux-commands-Shell-script/.git/info/exclude
OS-Linux-commands-Shell-script/.git/index
OS-Linux-commands-Shell-script/.git/branches/
OS-Linux-commands-Shell-script/.git/hooks/
OS-Linux-commands-Shell-script/.git/hooks/update.sample
OS-Linux-commands-Shell-script/.git/hooks/fsmonitor-watchman.sample
OS-Linux-commands-Shell-script/.git/hooks/pre-rebase.sample
OS-Linux-commands-Shell-script/.git/hooks/applypatch-msg.sample
OS-Linux-commands-Shell-script/.git/hooks/commit-msg.sample
OS-Linux-commands-Shell-script/.git/hooks/pre-push.sample
OS-Linux-commands-Shell-script/.git/hooks/prepare-commit-msg.sample
OS-Linux-commands-Shell-script/.git/hooks/pre-applypatch.sample
OS-Linux-commands-Shell-script/.git/hooks/pre-commit.sample
OS-Linux-commands-Shell-script/.git/hooks/pre-receive.sample
OS-Linux-commands-Shell-script/.git/hooks/post-update.sample
OS-Linux-commands-Shell-script/.git/hooks/push-to-checkout.sample
OS-Linux-commands-Shell-script/.git/hooks/pre-merge-commit.sample
OS-Linux-commands-Shell-script/.git/HEAD
OS-Linux-commands-Shell-script/.git/objects/
OS-Linux-commands-Shell-script/.git/objects/info/
OS-Linux-commands-Shell-script/.git/objects/pack/
OS-Linux-commands-Shell-script/.git/objects/pack/pack-ec36fa2c38f0d702b12329b43a753a363ab5d761.idx
OS-Linux-commands-Shell-script/.git/objects/pack/pack-ec36fa2c38f0d702b12329b43a753a363ab5d761.pack
OS-Linux-commands-Shell-script/.git/config
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 20-53-02.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-37-18.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-31-52.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-58-09.png
OS-Linux-commands-Shell-script/image.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-34-40.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-57-42.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-43-11.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-47-59.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 19-17-05.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 19-18-02.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 19-37-12.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-36-38.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-19-42.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-58-36.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-08-53.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-35-44.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 20-55-52.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-08-11.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-00-06.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-32-59.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-43-26.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-07-10.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-01-46.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 21-05-22.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-29-22.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 19-51-59.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-14-46.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-36-06.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 19-47-05.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 19-45-45.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-25-41.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 21-57-28.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-38-17.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-59-05.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-45-57.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-16-47.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 19-41-16.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-38-33.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-58-59.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-55-15.png
OS-Linux-commands-Shell-script/README.md
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-39-22.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-42-16.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-06-26.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-51-02.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-52-09.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-39-18.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-46-46.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 19-57-24.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-54-21.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-30-26.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 21-09-33.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 19-54-54.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-52-10.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-30-41.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-27-36.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-45-16.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-46-30.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 21-01-43.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-45-47.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 19-05-41.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-17-22.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-42-20.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 19-07-18.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-50-05.png
OS-Linux-commands-Shell-script/LICENSE
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-35-03.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-09-30.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-41-07.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-23-44.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-57-52.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-11-09.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-47-19.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-03-51.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 20-49-29.png
OS-Linux-commands-Shell-script/file1
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-15-24.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-15-10.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 20-40-27.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-41-04.png
palindrome.sh
psswdperm.sh
scriptest.sh
strcomp.sh
untiltest.sh
urllist.txt
whiletest
whiletest.sh
```

mkdir backupdir
 
mv backup.tar backupdir
 
tar -tvf backup.tar

## OUTPUT
```
-rw-rw-r-- sec/sec         219 2024-02-27 22:47 argshift1.sh
-rwxrwxrwx sec/sec          75 2024-02-27 22:49 argshift.sh
drwxrwxr-x sec/sec           0 2024-02-27 20:29 backupdir/
-rw-rw-r-- sec/sec          96 2024-02-26 20:02 backupdir/newfile
-rw-rw-r-- sec/sec         131 2024-02-26 21:40 backupdir/file21
drwxrwxr-x sec/sec           0 2024-02-27 19:01 backupdir/OS-Linux-commands-Shell-script/
-rw-rw-r-- sec/sec      262090 2024-02-27 18:53 backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-17-30.png
-rw-rw-r-- sec/sec      240704 2024-02-27 18:56 backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-12-39.png
-rw-rw-r-- sec/sec      106883 2024-02-27 18:58 backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-35-33.png
-rw-rw-r-- sec/sec      148546 2024-02-27 18:54 backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-32-26.png
-rw-rw-r-- sec/sec      118987 2024-02-26 20:04 backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-04-03.png
-rw-rw-r-- sec/sec      133902 2024-02-26 19:49 backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-49-33.png
-rw-rw-r-- sec/sec      131120 2024-02-26 20:05 backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-05-03.png
-rw-rw-r-- sec/sec      209726 2024-02-27 18:50 backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-13-35.png
-rw-rw-r-- sec/sec      117673 2024-02-27 18:58 backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-36-48.png
-rw-rw-r-- sec/sec      500934 2024-02-26 19:56 backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-56-15.png
-rw-rw-r-- sec/sec      103493 2024-02-27 18:53 backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-19-45.png
drwxrwxr-x sec/sec           0 2024-02-20 14:48 backupdir/OS-Linux-commands-Shell-script/.git/
-rw-rw-r-- sec/sec          73 2024-02-20 14:48 backupdir/OS-Linux-commands-Shell-script/.git/description
drwxrwxr-x sec/sec           0 2024-02-20 14:48 backupdir/OS-Linux-commands-Shell-script/.git/refs/
drwxrwxr-x sec/sec           0 2024-02-20 14:48 backupdir/OS-Linux-commands-Shell-script/.git/refs/tags/
drwxrwxr-x sec/sec           0 2024-02-20 14:48 backupdir/OS-Linux-commands-Shell-script/.git/refs/remotes/
drwxrwxr-x sec/sec           0 2024-02-20 14:48 backupdir/OS-Linux-commands-Shell-script/.git/refs/remotes/origin/
-rw-rw-r-- sec/sec          30 2024-02-20 14:48 backupdir/OS-Linux-commands-Shell-script/.git/refs/remotes/origin/HEAD
drwxrwxr-x sec/sec           0 2024-02-20 14:48 backupdir/OS-Linux-commands-Shell-script/.git/refs/heads/
-rw-rw-r-- sec/sec          41 2024-02-20 14:48 backupdir/OS-Linux-commands-Shell-script/.git/refs/heads/main
drwxrwxr-x sec/sec           0 2024-02-20 14:48 backupdir/OS-Linux-commands-Shell-script/.git/logs/
drwxrwxr-x sec/sec           0 2024-02-20 14:48 backupdir/OS-Linux-commands-Shell-script/.git/logs/refs/
drwxrwxr-x sec/sec           0 2024-02-20 14:48 backupdir/OS-Linux-commands-Shell-script/.git/logs/refs/remotes/
drwxrwxr-x sec/sec           0 2024-02-20 14:48 backupdir/OS-Linux-commands-Shell-script/.git/logs/refs/remotes/origin/
-rw-rw-r-- sec/sec         210 2024-02-20 14:48 backupdir/OS-Linux-commands-Shell-script/.git/logs/refs/remotes/origin/HEAD
drwxrwxr-x sec/sec           0 2024-02-20 14:48 backupdir/OS-Linux-commands-Shell-script/.git/logs/refs/heads/
-rw-rw-r-- sec/sec         210 2024-02-20 14:48 backupdir/OS-Linux-commands-Shell-script/.git/logs/refs/heads/main
-rw-rw-r-- sec/sec         210 2024-02-20 14:48 backupdir/OS-Linux-commands-Shell-script/.git/logs/HEAD
-rw-rw-r-- sec/sec         112 2024-02-20 14:48 backupdir/OS-Linux-commands-Shell-script/.git/packed-refs
drwxrwxr-x sec/sec           0 2024-02-20 14:48 backupdir/OS-Linux-commands-Shell-script/.git/info/
-rw-rw-r-- sec/sec         240 2024-02-20 14:48 backupdir/OS-Linux-commands-Shell-script/.git/info/exclude
-rw-rw-r-- sec/sec         209 2024-02-20 14:48 backupdir/OS-Linux-commands-Shell-script/.git/index
drwxrwxr-x sec/sec           0 2024-02-20 14:48 backupdir/OS-Linux-commands-Shell-script/.git/branches/
drwxrwxr-x sec/sec           0 2024-02-20 14:48 backupdir/OS-Linux-commands-Shell-script/.git/hooks/
-rwxrwxr-x sec/sec        3650 2024-02-20 14:48 backupdir/OS-Linux-commands-Shell-script/.git/hooks/update.sample
-rwxrwxr-x sec/sec        4655 2024-02-20 14:48 backupdir/OS-Linux-commands-Shell-script/.git/hooks/fsmonitor-watchman.sample
-rwxrwxr-x sec/sec        4898 2024-02-20 14:48 backupdir/OS-Linux-commands-Shell-script/.git/hooks/pre-rebase.sample
-rwxrwxr-x sec/sec         478 2024-02-20 14:48 backupdir/OS-Linux-commands-Shell-script/.git/hooks/applypatch-msg.sample
-rwxrwxr-x sec/sec         896 2024-02-20 14:48 backupdir/OS-Linux-commands-Shell-script/.git/hooks/commit-msg.sample
-rwxrwxr-x sec/sec        1374 2024-02-20 14:48 backupdir/OS-Linux-commands-Shell-script/.git/hooks/pre-push.sample
-rwxrwxr-x sec/sec        1492 2024-02-20 14:48 backupdir/OS-Linux-commands-Shell-script/.git/hooks/prepare-commit-msg.sample
-rwxrwxr-x sec/sec         424 2024-02-20 14:48 backupdir/OS-Linux-commands-Shell-script/.git/hooks/pre-applypatch.sample
-rwxrwxr-x sec/sec        1643 2024-02-20 14:48 backupdir/OS-Linux-commands-Shell-script/.git/hooks/pre-commit.sample
-rwxrwxr-x sec/sec         544 2024-02-20 14:48 backupdir/OS-Linux-commands-Shell-script/.git/hooks/pre-receive.sample
-rwxrwxr-x sec/sec         189 2024-02-20 14:48 backupdir/OS-Linux-commands-Shell-script/.git/hooks/post-update.sample
-rwxrwxr-x sec/sec        2783 2024-02-20 14:48 backupdir/OS-Linux-commands-Shell-script/.git/hooks/push-to-checkout.sample
-rwxrwxr-x sec/sec         416 2024-02-20 14:48 backupdir/OS-Linux-commands-Shell-script/.git/hooks/pre-merge-commit.sample
-rw-rw-r-- sec/sec          21 2024-02-20 14:48 backupdir/OS-Linux-commands-Shell-script/.git/HEAD
drwxrwxr-x sec/sec           0 2024-02-20 14:48 backupdir/OS-Linux-commands-Shell-script/.git/objects/
drwxrwxr-x sec/sec           0 2024-02-20 14:48 backupdir/OS-Linux-commands-Shell-script/.git/objects/info/
drwxrwxr-x sec/sec           0 2024-02-20 14:48 backupdir/OS-Linux-commands-Shell-script/.git/objects/pack/
-r--r--r-- sec/sec        2360 2024-02-20 14:48 backupdir/OS-Linux-commands-Shell-script/.git/objects/pack/pack-ec36fa2c38f0d702b12329b43a753a363ab5d761.idx
-r--r--r-- sec/sec       31423 2024-02-20 14:48 backupdir/OS-Linux-commands-Shell-script/.git/objects/pack/pack-ec36fa2c38f0d702b12329b43a753a363ab5d761.pack
-rw-rw-r-- sec/sec         279 2024-02-20 14:48 backupdir/OS-Linux-commands-Shell-script/.git/config
-rw-rw-r-- sec/sec      472198 2024-02-26 19:58 backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-58-09.png
-rw-rw-r-- sec/sec      500934 2024-02-26 19:56 backupdir/OS-Linux-commands-Shell-script/image.png
-rw-rw-r-- sec/sec       97798 2024-02-27 18:57 backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-34-40.png
-rw-rw-r-- sec/sec      512738 2024-02-26 19:57 backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-57-42.png
-rw-rw-r-- sec/sec       92278 2024-02-26 19:36 backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-36-38.png
-rw-rw-r-- sec/sec       78052 2024-02-27 18:57 backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-19-42.png
-rw-rw-r-- sec/sec      492050 2024-02-26 19:58 backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-58-36.png
-rw-rw-r-- sec/sec       92193 2024-02-26 19:35 backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-35-44.png
-rw-rw-r-- sec/sec      164543 2024-02-26 20:08 backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-08-11.png
-rw-rw-r-- sec/sec       83051 2024-02-26 20:00 backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-00-06.png
-rw-rw-r-- sec/sec      145160 2024-02-26 19:34 backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-32-59.png
-rw-rw-r-- sec/sec      133278 2024-02-27 19:00 backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-43-26.png
-rw-rw-r-- sec/sec      152534 2024-02-26 20:07 backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-07-10.png
-rw-rw-r-- sec/sec       98085 2024-02-26 19:29 backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-29-22.png
-rw-rw-r-- sec/sec      221650 2024-02-27 18:50 backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-14-46.png
-rw-rw-r-- sec/sec      174741 2024-02-27 18:54 backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-36-06.png
-rw-rw-r-- sec/sec      150194 2024-02-27 18:59 backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-38-17.png
-rw-rw-r-- sec/sec      234558 2024-02-27 18:55 backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-59-05.png
-rw-rw-r-- sec/sec      245535 2024-02-27 18:52 backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-16-47.png
-rw-rw-r-- sec/sec      105506 2024-02-26 19:38 backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-38-33.png
-rw-rw-r-- sec/sec      431163 2024-02-26 19:59 backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-58-59.png
-rw-rw-r-- sec/sec      511115 2024-02-26 19:55 backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-55-15.png
-rw-rw-r-- sec/sec       17456 2024-02-27 18:17 backupdir/OS-Linux-commands-Shell-script/README.md
-rw-rw-r-- sec/sec      115990 2024-02-26 19:39 backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-39-22.png
-rw-rw-r-- sec/sec      106952 2024-02-27 19:00 backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-42-16.png
-rw-rw-r-- sec/sec      143030 2024-02-26 20:06 backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-06-26.png
-rw-rw-r-- sec/sec       80717 2024-02-26 19:53 backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-51-02.png
-rw-rw-r-- sec/sec      174906 2024-02-27 18:59 backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-39-18.png
-rw-rw-r-- sec/sec      121595 2024-02-26 19:46 backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-46-46.png
-rw-rw-r-- sec/sec      133880 2024-02-26 19:31 backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-30-26.png
-rw-rw-r-- sec/sec      200916 2024-02-27 18:55 backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-52-10.png
-rw-rw-r-- sec/sec      121861 2024-02-27 18:53 backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-30-41.png
-rw-rw-r-- sec/sec      101960 2024-02-26 19:45 backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-45-16.png
-rw-rw-r-- sec/sec      107201 2024-02-27 19:01 backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-46-30.png
-rw-rw-r-- sec/sec      112238 2024-02-26 19:46 backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-45-47.png
-rw-rw-r-- sec/sec       78797 2024-02-26 21:18 backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-17-22.png
-rw-rw-r-- sec/sec       35149 2024-02-20 14:48 backupdir/OS-Linux-commands-Shell-script/LICENSE
-rw-rw-r-- sec/sec      176710 2024-02-26 20:09 backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-09-30.png
-rw-rw-r-- sec/sec      105845 2024-02-27 18:59 backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-41-07.png
-rw-rw-r-- sec/sec       82644 2024-02-27 18:57 backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-23-44.png
-rw-rw-r-- sec/sec      219250 2024-02-27 18:55 backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-57-52.png
-rw-rw-r-- sec/sec      191287 2024-02-27 18:49 backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-11-09.png
-rw-rw-r-- sec/sec       82097 2024-02-26 21:47 backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-47-19.png
-rw-rw-r-- sec/sec          62 2024-02-26 22:47 backupdir/OS-Linux-commands-Shell-script/file1
-rw-rw-r-- sec/sec      233660 2024-02-27 18:52 backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-15-24.png
-rw-rw-r-- sec/sec       81662 2024-02-26 19:41 backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-41-04.png
-rw-rw-r-- sec/sec         155 2024-02-26 21:41 backupdir/file22
-rw-rw-r-- sec/sec         210 2024-02-26 20:19 backupdir/file23
-rw-rw-r-- sec/sec          52 2024-02-26 21:45 backupdir/urllist.txt
-rw-rw-r-- sec/sec    10240000 2024-02-27 19:05 backupdir/backup.tar
-rw-rw-r-- sec/sec          29 2024-02-26 19:37 backupdir/file11
-rw-rw-r-- sec/sec          70 2024-02-26 19:30 backupdir/file2
-rw-rw-r-- sec/sec          61 2024-02-26 19:27 backupdir/file1
-rwxr-xr-x sec/sec         251 2024-02-27 21:56 casecheck.sh
-rw-rw-r-- sec/sec          64 2024-02-27 22:21 cities
-rw-rw-r-- sec/sec          85 2024-02-27 22:51 data.dat
-rwxr-xr-x sec/sec         360 2024-02-27 21:07 elifcheck.sh
-rwxr-xr-x sec/sec         118 2024-02-27 22:38 exread1.sh
-rwxr-xr-x sec/sec         121 2024-02-27 22:36 exread.sh
-rw-rw-r-- sec/sec          61 2024-02-26 19:27 file1
-rw-rw-r-- sec/sec          29 2024-02-26 19:37 file11
-rw-rw-r-- sec/sec          70 2024-02-26 19:30 file2
-rw-rw-r-- sec/sec         131 2024-02-26 21:40 file21
-rw-rw-r-- sec/sec         155 2024-02-26 21:41 file22
-rw-rw-r-- sec/sec         210 2024-02-26 20:19 file23
-rwxr-xr-x sec/sec         170 2024-02-27 22:31 forbreak.sh
-rwxr-xr-x sec/sec          93 2024-02-27 22:24 forctype.sh
-rwxr-xr-x sec/sec         132 2024-02-27 22:05 forin1.sh
-rwxr-xr-x sec/sec         135 2024-02-27 22:07 forin2.sh
-rwxr-xr-x sec/sec         151 2024-02-27 22:11 forin3.sh
-rwxrwxrwx sec/sec         119 2024-02-27 22:18 forinfile.sh
-rwxr-xr-x sec/sec         155 2024-02-27 22:26 fornested1.sh
-rw-rw-r-- sec/sec         206 2024-02-27 22:41 funcex.sh
-rw-rw-r-- sec/sec          60 2024-02-27 19:36 herecheck.txt
-rwxr-xr-x sec/sec         138 2024-02-27 21:10 ifcompound.sh
-rw-rw-r-- sec/sec         322 2024-02-27 20:56 ifnested1.sh
-rwxr-xr-x sec/sec         321 2024-02-27 21:03 ifnested.sh
-rwxr-xr-x sec/sec         209 2024-02-27 21:00 iftest.sh
-rwxr-xr-x sec/sec           0 2024-02-27 19:32 my-script.sh
-rw-rw-r-- sec/sec         177 2024-02-27 22:50 nc.awk
-rw-rw-r-- sec/sec          96 2024-02-26 20:02 newfile
-rw-rw-r-- sec/sec           6 2024-02-27 20:39 one
drwxrwxr-x sec/sec           0 2024-02-27 22:54 OS-Linux-commands-Shell-script/
-rw-rw-r-- sec/sec      415062 2024-02-27 19:14 OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 19-12-09.png
-rw-rw-r-- sec/sec       60477 2024-02-27 22:06 OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-06-20.png
-rw-rw-r-- sec/sec       64961 2024-02-27 22:40 OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-40-20.png
-rw-rw-r-- sec/sec       35736 2024-02-27 22:16 OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-16-41.png
-rw-rw-r-- sec/sec      262090 2024-02-27 18:53 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-17-30.png
-rw-rw-r-- sec/sec      240704 2024-02-27 18:56 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-12-39.png
-rw-rw-r-- sec/sec      107201 2024-02-27 19:06 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-46-30-1.png
-rw-rw-r-- sec/sec      106883 2024-02-27 18:58 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-35-33.png
-rw-rw-r-- sec/sec       97317 2024-02-27 20:12 OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 20-11-56.png
-rw-rw-r-- sec/sec      148546 2024-02-27 18:54 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-32-26.png
-rw-rw-r-- sec/sec      118987 2024-02-26 20:04 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-04-03.png
-rw-rw-r-- sec/sec      133902 2024-02-26 19:49 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-49-33.png
-rw-rw-r-- sec/sec      479827 2024-02-27 19:16 OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 19-16-26.png
-rw-rw-r-- sec/sec       81079 2024-02-27 20:11 OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 20-11-08.png
-rw-rw-r-- sec/sec      106070 2024-02-27 19:35 OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 19-34-51.png
-rw-rw-r-- sec/sec      131120 2024-02-26 20:05 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-05-03.png
-rw-rw-r-- sec/sec      209726 2024-02-27 18:50 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-13-35.png
-rw-rw-r-- sec/sec      117673 2024-02-27 18:58 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-36-48.png
-rw-rw-r-- sec/sec       65004 2024-02-27 19:52 OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 19-52-43.png
-rw-rw-r-- sec/sec      500934 2024-02-26 19:56 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-56-15.png
-rw-rw-r-- sec/sec      103493 2024-02-27 18:53 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-19-45.png
-rw-rw-r-- sec/sec       49691 2024-02-27 21:11 OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 21-11-27.png
drwxrwxr-x sec/sec           0 2024-02-20 14:48 OS-Linux-commands-Shell-script/.git/
-rw-rw-r-- sec/sec          73 2024-02-20 14:48 OS-Linux-commands-Shell-script/.git/description
drwxrwxr-x sec/sec           0 2024-02-20 14:48 OS-Linux-commands-Shell-script/.git/refs/
drwxrwxr-x sec/sec           0 2024-02-20 14:48 OS-Linux-commands-Shell-script/.git/refs/tags/
drwxrwxr-x sec/sec           0 2024-02-20 14:48 OS-Linux-commands-Shell-script/.git/refs/remotes/
drwxrwxr-x sec/sec           0 2024-02-20 14:48 OS-Linux-commands-Shell-script/.git/refs/remotes/origin/
-rw-rw-r-- sec/sec          30 2024-02-20 14:48 OS-Linux-commands-Shell-script/.git/refs/remotes/origin/HEAD
drwxrwxr-x sec/sec           0 2024-02-20 14:48 OS-Linux-commands-Shell-script/.git/refs/heads/
-rw-rw-r-- sec/sec          41 2024-02-20 14:48 OS-Linux-commands-Shell-script/.git/refs/heads/main
drwxrwxr-x sec/sec           0 2024-02-20 14:48 OS-Linux-commands-Shell-script/.git/logs/
drwxrwxr-x sec/sec           0 2024-02-20 14:48 OS-Linux-commands-Shell-script/.git/logs/refs/
drwxrwxr-x sec/sec           0 2024-02-20 14:48 OS-Linux-commands-Shell-script/.git/logs/refs/remotes/
drwxrwxr-x sec/sec           0 2024-02-20 14:48 OS-Linux-commands-Shell-script/.git/logs/refs/remotes/origin/
-rw-rw-r-- sec/sec         210 2024-02-20 14:48 OS-Linux-commands-Shell-script/.git/logs/refs/remotes/origin/HEAD
drwxrwxr-x sec/sec           0 2024-02-20 14:48 OS-Linux-commands-Shell-script/.git/logs/refs/heads/
-rw-rw-r-- sec/sec         210 2024-02-20 14:48 OS-Linux-commands-Shell-script/.git/logs/refs/heads/main
-rw-rw-r-- sec/sec         210 2024-02-20 14:48 OS-Linux-commands-Shell-script/.git/logs/HEAD
-rw-rw-r-- sec/sec         112 2024-02-20 14:48 OS-Linux-commands-Shell-script/.git/packed-refs
drwxrwxr-x sec/sec           0 2024-02-20 14:48 OS-Linux-commands-Shell-script/.git/info/
-rw-rw-r-- sec/sec         240 2024-02-20 14:48 OS-Linux-commands-Shell-script/.git/info/exclude
-rw-rw-r-- sec/sec         209 2024-02-20 14:48 OS-Linux-commands-Shell-script/.git/index
drwxrwxr-x sec/sec           0 2024-02-20 14:48 OS-Linux-commands-Shell-script/.git/branches/
drwxrwxr-x sec/sec           0 2024-02-20 14:48 OS-Linux-commands-Shell-script/.git/hooks/
-rwxrwxr-x sec/sec        3650 2024-02-20 14:48 OS-Linux-commands-Shell-script/.git/hooks/update.sample
-rwxrwxr-x sec/sec        4655 2024-02-20 14:48 OS-Linux-commands-Shell-script/.git/hooks/fsmonitor-watchman.sample
-rwxrwxr-x sec/sec        4898 2024-02-20 14:48 OS-Linux-commands-Shell-script/.git/hooks/pre-rebase.sample
-rwxrwxr-x sec/sec         478 2024-02-20 14:48 OS-Linux-commands-Shell-script/.git/hooks/applypatch-msg.sample
-rwxrwxr-x sec/sec         896 2024-02-20 14:48 OS-Linux-commands-Shell-script/.git/hooks/commit-msg.sample
-rwxrwxr-x sec/sec        1374 2024-02-20 14:48 OS-Linux-commands-Shell-script/.git/hooks/pre-push.sample
-rwxrwxr-x sec/sec        1492 2024-02-20 14:48 OS-Linux-commands-Shell-script/.git/hooks/prepare-commit-msg.sample
-rwxrwxr-x sec/sec         424 2024-02-20 14:48 OS-Linux-commands-Shell-script/.git/hooks/pre-applypatch.sample
-rwxrwxr-x sec/sec        1643 2024-02-20 14:48 OS-Linux-commands-Shell-script/.git/hooks/pre-commit.sample
-rwxrwxr-x sec/sec         544 2024-02-20 14:48 OS-Linux-commands-Shell-script/.git/hooks/pre-receive.sample
-rwxrwxr-x sec/sec         189 2024-02-20 14:48 OS-Linux-commands-Shell-script/.git/hooks/post-update.sample
-rwxrwxr-x sec/sec        2783 2024-02-20 14:48 OS-Linux-commands-Shell-script/.git/hooks/push-to-checkout.sample
-rwxrwxr-x sec/sec         416 2024-02-20 14:48 OS-Linux-commands-Shell-script/.git/hooks/pre-merge-commit.sample
-rw-rw-r-- sec/sec          21 2024-02-20 14:48 OS-Linux-commands-Shell-script/.git/HEAD
drwxrwxr-x sec/sec           0 2024-02-20 14:48 OS-Linux-commands-Shell-script/.git/objects/
drwxrwxr-x sec/sec           0 2024-02-20 14:48 OS-Linux-commands-Shell-script/.git/objects/info/
drwxrwxr-x sec/sec           0 2024-02-20 14:48 OS-Linux-commands-Shell-script/.git/objects/pack/
-r--r--r-- sec/sec        2360 2024-02-20 14:48 OS-Linux-commands-Shell-script/.git/objects/pack/pack-ec36fa2c38f0d702b12329b43a753a363ab5d761.idx
-r--r--r-- sec/sec       31423 2024-02-20 14:48 OS-Linux-commands-Shell-script/.git/objects/pack/pack-ec36fa2c38f0d702b12329b43a753a363ab5d761.pack
-rw-rw-r-- sec/sec         279 2024-02-20 14:48 OS-Linux-commands-Shell-script/.git/config
-rw-rw-r-- sec/sec       66005 2024-02-27 20:53 OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 20-53-02.png
-rw-rw-r-- sec/sec       62727 2024-02-27 22:37 OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-37-18.png
-rw-rw-r-- sec/sec       63548 2024-02-27 22:32 OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-31-52.png
-rw-rw-r-- sec/sec      472198 2024-02-26 19:58 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-58-09.png
-rw-rw-r-- sec/sec      500934 2024-02-26 19:56 OS-Linux-commands-Shell-script/image.png
-rw-rw-r-- sec/sec       97798 2024-02-27 18:57 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-34-40.png
-rw-rw-r-- sec/sec      512738 2024-02-26 19:57 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-57-42.png
-rw-rw-r-- sec/sec       58127 2024-02-27 22:43 OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-43-11.png
-rw-rw-r-- sec/sec       71506 2024-02-27 22:48 OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-47-59.png
-rw-rw-r-- sec/sec      330018 2024-02-27 19:17 OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 19-17-05.png
-rw-rw-r-- sec/sec      402775 2024-02-27 19:18 OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 19-18-02.png
-rw-rw-r-- sec/sec      136310 2024-02-27 19:37 OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 19-37-12.png
-rw-rw-r-- sec/sec       92278 2024-02-26 19:36 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-36-38.png
-rw-rw-r-- sec/sec       78052 2024-02-27 18:57 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-19-42.png
-rw-rw-r-- sec/sec      492050 2024-02-26 19:58 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-58-36.png
-rw-rw-r-- sec/sec       50439 2024-02-27 22:09 OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-08-53.png
-rw-rw-r-- sec/sec       92193 2024-02-26 19:35 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-35-44.png
-rw-rw-r-- sec/sec      107502 2024-02-27 20:59 OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 20-55-52.png
-rw-rw-r-- sec/sec      164543 2024-02-26 20:08 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-08-11.png
-rw-rw-r-- sec/sec       83051 2024-02-26 20:00 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-00-06.png
-rw-rw-r-- sec/sec      145160 2024-02-26 19:34 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-32-59.png
-rw-rw-r-- sec/sec      133278 2024-02-27 19:00 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-43-26.png
-rw-rw-r-- sec/sec      152534 2024-02-26 20:07 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-07-10.png
-rw-rw-r-- sec/sec       50774 2024-02-27 22:02 OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-01-46.png
-rw-rw-r-- sec/sec      124175 2024-02-27 21:05 OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 21-05-22.png
-rw-rw-r-- sec/sec       98085 2024-02-26 19:29 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-29-22.png
-rw-rw-r-- sec/sec       25282 2024-02-27 19:52 OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 19-51-59.png
-rw-rw-r-- sec/sec      221650 2024-02-27 18:50 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-14-46.png
-rw-rw-r-- sec/sec      174741 2024-02-27 18:54 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-36-06.png
-rw-rw-r-- sec/sec       14599 2024-02-27 19:47 OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 19-47-05.png
-rw-rw-r-- sec/sec       18024 2024-02-27 19:45 OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 19-45-45.png
-rw-rw-r-- sec/sec       57978 2024-02-27 22:26 OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-25-41.png
-rw-rw-r-- sec/sec       61922 2024-02-27 21:57 OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 21-57-28.png
-rw-rw-r-- sec/sec      150194 2024-02-27 18:59 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-38-17.png
-rw-rw-r-- sec/sec      234558 2024-02-27 18:55 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-59-05.png
-rw-rw-r-- sec/sec       65392 2024-02-27 22:46 OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-45-57.png
-rw-rw-r-- sec/sec      245535 2024-02-27 18:52 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-16-47.png
-rw-rw-r-- sec/sec      183907 2024-02-27 19:41 OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 19-41-16.png
-rw-rw-r-- sec/sec      105506 2024-02-26 19:38 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-38-33.png
-rw-rw-r-- sec/sec      431163 2024-02-26 19:59 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-58-59.png
-rw-rw-r-- sec/sec      511115 2024-02-26 19:55 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-55-15.png
-rw-rw-r-- sec/sec       17456 2024-02-27 18:17 OS-Linux-commands-Shell-script/README.md
-rw-rw-r-- sec/sec      115990 2024-02-26 19:39 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-39-22.png
-rw-rw-r-- sec/sec      106952 2024-02-27 19:00 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-42-16.png
-rw-rw-r-- sec/sec      143030 2024-02-26 20:06 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-06-26.png
-rw-rw-r-- sec/sec       80717 2024-02-26 19:53 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-51-02.png
-rw-rw-r-- sec/sec       94416 2024-02-27 22:52 OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-52-09.png
-rw-rw-r-- sec/sec      174906 2024-02-27 18:59 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-39-18.png
-rw-rw-r-- sec/sec      121595 2024-02-26 19:46 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-46-46.png
-rw-rw-r-- sec/sec       31854 2024-02-27 19:57 OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 19-57-24.png
-rw-rw-r-- sec/sec       71136 2024-02-27 22:54 OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-54-21.png
-rw-rw-r-- sec/sec      133880 2024-02-26 19:31 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-30-26.png
-rw-rw-r-- sec/sec       69477 2024-02-27 21:09 OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 21-09-33.png
-rw-rw-r-- sec/sec       56221 2024-02-27 19:55 OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 19-54-54.png
-rw-rw-r-- sec/sec      200916 2024-02-27 18:55 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-52-10.png
-rw-rw-r-- sec/sec      121861 2024-02-27 18:53 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-30-41.png
-rw-rw-r-- sec/sec       76428 2024-02-27 22:27 OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-27-36.png
-rw-rw-r-- sec/sec      101960 2024-02-26 19:45 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-45-16.png
-rw-rw-r-- sec/sec      107201 2024-02-27 19:01 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-46-30.png
-rw-rw-r-- sec/sec       92015 2024-02-27 21:02 OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 21-01-43.png
-rw-rw-r-- sec/sec      112238 2024-02-26 19:46 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-45-47.png
-rw-rw-r-- sec/sec      326756 2024-02-27 19:06 OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 19-05-41.png
-rw-rw-r-- sec/sec       78797 2024-02-26 21:18 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-17-22.png
-rw-rw-r-- sec/sec       48319 2024-02-27 22:42 OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-42-20.png
-rw-rw-r-- sec/sec      397024 2024-02-27 19:07 OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 19-07-18.png
-rw-rw-r-- sec/sec       47796 2024-02-27 22:50 OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-50-05.png
-rw-rw-r-- sec/sec       35149 2024-02-20 14:48 OS-Linux-commands-Shell-script/LICENSE
-rw-rw-r-- sec/sec       90722 2024-02-27 22:35 OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-35-03.png
-rw-rw-r-- sec/sec      176710 2024-02-26 20:09 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-09-30.png
-rw-rw-r-- sec/sec      105845 2024-02-27 18:59 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-41-07.png
-rw-rw-r-- sec/sec       82644 2024-02-27 18:57 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-23-44.png
-rw-rw-r-- sec/sec      219250 2024-02-27 18:55 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-57-52.png
-rw-rw-r-- sec/sec      191287 2024-02-27 18:49 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-11-09.png
-rw-rw-r-- sec/sec       82097 2024-02-26 21:47 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-47-19.png
-rw-rw-r-- sec/sec       58644 2024-02-27 22:04 OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-03-51.png
-rw-rw-r-- sec/sec       52702 2024-02-27 20:49 OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 20-49-29.png
-rw-rw-r-- sec/sec          62 2024-02-26 22:47 OS-Linux-commands-Shell-script/file1
-rw-rw-r-- sec/sec      233660 2024-02-27 18:52 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-15-24.png
-rw-rw-r-- sec/sec       34932 2024-02-27 22:15 OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-15-10.png
-rw-rw-r-- sec/sec       44678 2024-02-27 20:40 OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 20-40-27.png
-rw-rw-r-- sec/sec       81662 2024-02-26 19:41 OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-41-04.png
-rw-rw-r-- sec/sec         350 2024-02-27 22:53 palindrome.sh
-rw-rw-r-- sec/sec         164 2024-02-27 20:51 psswdperm.sh
-rwxrwxrwx sec/sec         260 2024-02-27 20:27 scriptest.sh
-rwxr-xr-x sec/sec         140 2024-02-27 20:47 strcomp.sh
-rwxr-xr-x sec/sec          96 2024-02-27 22:03 untiltest.sh
-rw-rw-r-- sec/sec          52 2024-02-26 21:45 urllist.txt
-rw-rw-r-- sec/sec         101 2024-02-27 22:00 whiletest
-rwxr-xr-x sec/sec         101 2024-02-27 22:01 whiletest.sh
```

tar -xvf backup.tar
## OUTPUT
```
argshift1.sh
argshift.sh
backupdir/
backupdir/newfile
backupdir/file21
backupdir/OS-Linux-commands-Shell-script/
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-17-30.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-12-39.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-35-33.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-32-26.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-04-03.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-49-33.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-05-03.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-13-35.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-36-48.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-56-15.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-19-45.png
backupdir/OS-Linux-commands-Shell-script/.git/
backupdir/OS-Linux-commands-Shell-script/.git/description
backupdir/OS-Linux-commands-Shell-script/.git/refs/
backupdir/OS-Linux-commands-Shell-script/.git/refs/tags/
backupdir/OS-Linux-commands-Shell-script/.git/refs/remotes/
backupdir/OS-Linux-commands-Shell-script/.git/refs/remotes/origin/
backupdir/OS-Linux-commands-Shell-script/.git/refs/remotes/origin/HEAD
backupdir/OS-Linux-commands-Shell-script/.git/refs/heads/
backupdir/OS-Linux-commands-Shell-script/.git/refs/heads/main
backupdir/OS-Linux-commands-Shell-script/.git/logs/
backupdir/OS-Linux-commands-Shell-script/.git/logs/refs/
backupdir/OS-Linux-commands-Shell-script/.git/logs/refs/remotes/
backupdir/OS-Linux-commands-Shell-script/.git/logs/refs/remotes/origin/
backupdir/OS-Linux-commands-Shell-script/.git/logs/refs/remotes/origin/HEAD
backupdir/OS-Linux-commands-Shell-script/.git/logs/ref
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-34-40.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-57-42.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-36-38.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-19-42.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-58-36.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-35-44.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-08-11.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-00-06.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-32-59.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-43-26.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-07-10.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-29-22.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-14-46.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-36-06.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-38-17.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-59-05.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-16-47.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-38-33.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-58-59.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-55-15.png
backupdir/OS-Linux-commands-Shell-script/README.md
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-39-22.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-42-16.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-06-26.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-51-02.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-39-18.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-46-46.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-30-26.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-52-10.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-30-41.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-45-16.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-46-30.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-45-47.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-17-22.png
backupdir/OS-Linux-commands-Shell-script/LICENSE
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-09-30.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-41-07.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-23-44.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-57-52.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-11-09.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-47-19.png
backupdir/OS-Linux-commands-Shell-script/file1
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-15-24.png
backupdir/OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-41-04.png
backupdir/file22
backupdir/file23
backupdir/urllist.txt
backupdir/backup.tar
backupdir/file11
backupdir/file2
backupdir/file1
casecheck.sh
cities
data.dat
elifcheck.sh
exread1.sh
exread.sh
file1
file11
file2
file21
file22
file23
forbreak.sh
forctype.sh
forin1.sh
forin2.sh
forin3.sh
forinfile.sh
fornested1.sh
funcex.sh
herecheck.txt
ifcompound.sh
ifnested1.sh
ifnested.sh
iftest.sh
my-script.sh
nc.awk
newfile
one
OS-Linux-commands-Shell-script/
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 19-12-09.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-06-20.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-40-20.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-16-41.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-17-30.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-12-39.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-46-30-1.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-35-33.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 20-11-56.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-32-26.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-04-03.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-49-33.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 19-16-26.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 20-11-08.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 19-34-51.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-05-03.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-13-35.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-36-48.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 19-52-43.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-56-15.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-19-45.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 21-11-27.png
OS-Linux-commands-Shell-script/.git/
OS-Linux-commands-Shell-script/.git/description
OS-Linux-commands-Shell-script/.git/refs/
OS-Linux-commands-Shell-script/.git/refs/tags/
OS-Linux-commands-Shell-script/.git/refs/remotes/
OS-Linux-commands-Shell-script/.git/refs/remotes/origin/
OS-Linux-commands-Shell-script/.git/refs/remotes/origin/HEAD
OS-Linux-commands-Shell-script/.git/refs/heads/
OS-Linux-commands-Shell-script/.git/refs/heads/main
OS-Linux-commands-Shell-script/.git/logs/
OS-Linux-commands-Shell-script/.git/logs/refs/
OS-Linux-commands-Shell-script/.git/logs/refs/remotes/
OS-Linux-commands-Shell-script/.git/logs/refs/remotes/origin/
OS-Linux-commands-Shell-script/.git/logs/refs/remotes/origin/HEAD
OS-Linux-commands-Shell-script/.git/logs/refs/heads/
OS-Linux-commands-Shell-script/.git/logs/refs/heads/main
OS-Linux-commands-Shell-script/.git/logs/HEAD
OS-Linux-commands-Shell-script/.git/packed-refs
OS-Linux-commands-Shell-script/.git/info/
OS-Linux-commands-Shell-script/.git/info/exclude
OS-Linux-commands-Shell-script/.git/index
OS-Linux-commands-Shell-script/.git/branches/
OS-Linux-commands-Shell-script/.git/hooks/
OS-Linux-commands-Shell-script/.git/hooks/update.sample
OS-Linux-commands-Shell-script/.git/hooks/fsmonitor-watchman.sample
OS-Linux-commands-Shell-script/.git/hooks/pre-rebase.sample
OS-Linux-commands-Shell-script/.git/hooks/applypatch-msg.sample
OS-Linux-commands-Shell-script/.git/hooks/commit-msg.sample
OS-Linux-commands-Shell-script/.git/hooks/pre-push.sample
OS-Linux-commands-Shell-script/.git/hooks/prepare-commit-msg.sample
OS-Linux-commands-Shell-script/.git/hooks/pre-applypatch.sample
OS-Linux-commands-Shell-script/.git/hooks/pre-commit.sample
OS-Linux-commands-Shell-script/.git/hooks/pre-receive.sample
OS-Linux-commands-Shell-script/.git/hooks/post-update.sample
OS-Linux-commands-Shell-script/.git/hooks/push-to-checkout.sample
OS-Linux-commands-Shell-script/.git/hooks/pre-merge-commit.sample
OS-Linux-commands-Shell-script/.git/HEAD
OS-Linux-commands-Shell-script/.git/objects/
OS-Linux-commands-Shell-script/.git/objects/info/
OS-Linux-commands-Shell-script/.git/objects/pack/
OS-Linux-commands-Shell-script/.git/objects/pack/pack-ec36fa2c38f0d702b12329b43a753a363ab5d761.idx
OS-Linux-commands-Shell-script/.git/objects/pack/pack-ec36fa2c38f0d702b12329b43a753a363ab5d761.pack
OS-Linux-commands-Shell-script/.git/config
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 20-53-02.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-37-18.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-31-52.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-58-09.png
OS-Linux-commands-Shell-script/image.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-34-40.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-57-42.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-43-11.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-47-59.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 19-17-05.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 19-18-02.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 19-37-12.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-36-38.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-19-42.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-58-36.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-08-53.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-35-44.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 20-55-52.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-08-11.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-00-06.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-32-59.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-43-26.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-07-10.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-01-46.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 21-05-22.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-29-22.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 19-51-59.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-14-46.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-36-06.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 19-47-05.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 19-45-45.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-25-41.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 21-57-28.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-38-17.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-59-05.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-45-57.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-16-47.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 19-41-16.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-38-33.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-58-59.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-55-15.png
OS-Linux-commands-Shell-script/README.md
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-39-22.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-42-16.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-06-26.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-51-02.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-52-09.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-39-18.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-46-46.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 19-57-24.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-54-21.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-30-26.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 21-09-33.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 19-54-54.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-52-10.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-30-41.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-27-36.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-45-16.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-46-30.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 21-01-43.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-45-47.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 19-05-41.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-17-22.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-42-20.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 19-07-18.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-50-05.png
OS-Linux-commands-Shell-script/LICENSE
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-35-03.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-09-30.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-41-07.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-23-44.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-57-52.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-11-09.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 21-47-19.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-03-51.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 20-49-29.png
OS-Linux-commands-Shell-script/file1
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 20-15-24.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 22-15-10.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-27 20-40-27.png
OS-Linux-commands-Shell-script/Screenshot from 2024-02-26 19-41-04.png
palindrome.sh
psswdperm.sh
scriptest.sh
strcomp.sh
untiltest.sh
urllist.txt
whiletest
whiletest.sh
```

gzip backup.tar

ls .gz

## OUTPUT
 ```
 argshift1.sh   file11        fornested1.sh  OS-Linux-commands-Shell-script
argshift.sh    file2         funcex.sh      palindrome.sh
backupdir      file21        herecheck.txt  psswdperm.sh
backup.tar.gz  file22        ifcompound.sh  scriptest.sh
casecheck.sh   file23        ifnested1.sh   strcomp.sh
cities         forbreak.sh   ifnested.sh    untiltest.sh
data.dat       forctype.sh   iftest.sh      urllist.txt
elifcheck.sh   forin1.sh     my-script.sh   whiletest
exread1.sh     forin2.sh     nc.awk         whiletest.sh
exread.sh      forin3.sh     newfile
file1          forinfile.sh  one
```

gunzip backup.tar.gz

## OUTPUT
```
argshift1.sh   file11        fornested1.sh  OS-Linux-commands-Shell-script
argshift.sh    file2         funcex.sh      palindrome.sh
backupdir      file21        herecheck.txt  psswdperm.sh
backup.tar.gz  file22        ifcompound.sh  scriptest.sh
casecheck.sh   file23        ifnested1.sh   strcomp.sh
cities         forbreak.sh   ifnested.sh    untiltest.sh
data.dat       forctype.sh   iftest.sh      urllist.txt
elifcheck.sh   forin1.sh     my-script.sh   whiletest
exread1.sh     forin2.sh     nc.awk         whiletest.sh
exread.sh      forin3.sh     newfile
file1          forinfile.sh  one
(base) sec@sec-ThinkPad-E15-Gen-4:~/os/ex01/backupdir$ gunzip backup.tar.gz
(base) sec@sec-ThinkPad-E15-Gen-4:~/os/ex01/backupdir$ ls
argshift1.sh  file11        fornested1.sh  OS-Linux-commands-Shell-script
argshift.sh   file2         funcex.sh      palindrome.sh
backupdir     file21        herecheck.txt  psswdperm.sh
backup.tar    file22        ifcompound.sh  scriptest.sh
casecheck.sh  file23        ifnested1.sh   strcomp.sh
cities        forbreak.sh   ifnested.sh    untiltest.sh
data.dat      forctype.sh   iftest.sh      urllist.txt
elifcheck.sh  forin1.sh     my-script.sh   whiletest
exread1.sh    forin2.sh     nc.awk         whiletest.sh
exread.sh     forin3.sh     newfile
file1         forinfile.sh  one

```
 
# Shell Script

```
echo '#!/bin/sh' > my-script.sh

echo 'echo Hello World‘; exit 0 >> my-script.sh
```
chmod 755 my-script.sh

./my-script.sh

## OUTPUT
```
```
 
cat << stop > herecheck.txt
```
hello in- this world
i cant stop
for this non stop movement
stop
```

cat herecheck.txt

## OUTPUT
```
hello in- this world
i cant stop
for this non stop movement
```

cat < scriptest.sh 
```bash
\#!/bin/sh
echo “File name is $0 ”
echo "File name is " `basename $0`
echo “First arg. is ” $1
echo “Second arg. is ” $2
echo “Third arg. is ” $3
echo “Fourth arg. is ” $4
echo 'The $@ is ' $@
echo 'The $\# is ' $1#
echo 'The $$ is ' $$
ps
^d
```

cat scriptest.sh 

```bash
\#!/bin/sh
echo “File name is $0 ”
echo "File name is " `basename $0`
echo “First arg. is ” $1
echo “Second arg. is ” $2
echo “Third arg. is ” $3
echo “Fourth arg. is ” $4
echo 'The $@ is ' $@
echo 'The $\# is ' $\#
echo 'The $$ is ' $$
ps
```
 
chmod 777 scriptest.sh
 
./scriptest.sh 1 2 3

## OUTPUT
```
./scriptest.sh: line 1: #!/bin/sh: No such file or directory
“File name is ./scriptest.sh ”
File name is  scriptest.sh
“First arg. is ” 1
“Second arg. is ” 2
“Third arg. is ” 3
“Fourth arg. is ”
The $@ is  1 2 3
The $\# is  1#
The $$ is  14337
    PID TTY          TIME CMD
  13614 pts/1    00:00:00 bash
  14337 pts/1    00:00:00 bash
  14340 pts/1    00:00:00 ps
```
 
ls file1

## OUTPUT
```
file1
```

echo $?

## OUTPUT 
```
0
```

./one

bash: ./one: Permission denied
 
echo $?

## OUTPUT 
```
127
```

abcd
 
echo $?

## OUTPUT
```
127
```
 
# mis-using string comparisons

cat < strcomp.sh 
```bash
\#!/bin/bash
val1=baseball
val2=hockey
if [ $val1 \> $val2 ]
then
echo "$val1 is greater than $val2"
else
echo "$val1 is less than $val2"
fi
^d
```

cat strcomp.sh 
```bash
\#!/bin/bash
val1=baseball
val2=hockey
if [ $val1 \> $val2 ]
then
echo "$val1 is greater than $val2"
else
echo "$val1 is less than $val2"
fi
```

chmod 755 strcomp.sh

./strcomp.sh 

## OUTPUT
```
./strcomp.sh: line 1: #!/bin/bash: No such file or directory
baseball is less than hockey
./strcomp.sh: line 10: ^d: command not found
```

# Check file ownership

cat < psswdperm.sh 
```bash
\#!/bin/bash
if [ -O /etc/passwd ]
then
echo “You are the owner of the /etc/passwd file”
else
echo “Sorry, you are not the owner of the /etc/passwd file”
fi
^d
```

cat psswdperm.sh 
```bash
/#!/bin/bash
if [ -O /etc/passwd ]
then
echo “You are the owner of the /etc/passwd file”
else
echo “Sorry, you are not the owner of the /etc/passwd file”
fi
 ```
./psswdperm.sh

## OUTPUT
```
bash: ./psswdperm.sh: Permission denied
```

# Check if with file location

cat>ifnested.sh 
```bash
\#!/bin/bash
if [ -e $HOME ]
then
echo “$HOME The object exists, is it a file?”
if [ -f $HOME ]
then
echo “Yes,$HOME it is a file!”
else
echo “No,$HOME it is not a file!”
if [ -f $HOME/.bash_history ]
then
echo “But $HOME/.bash_history is a file!”
fi
fi
else
echo “Sorry, the object does not exist”
fi
^d
```
cat ifnested.sh 
```
\#!/bin/bash
if [ -e $HOME ]
then
echo “$HOME The object exists, is it a file?”
if [ -f $HOME ]
then
echo “Yes,$HOME it is a file!”
else
echo “No,$HOME it is not a file!”
if [ -f $HOME/.bash_history ]
then
echo “But $HOME/.bash_history is a file!”
fi
fi
else
echo “Sorry, the object does not exist”
fi
```

./ifnested.sh 
## OUTPUT
```
./ifnested.sh: line 1: #!/bin/bash: No such file or directory
“/home/sec The object exists, is it a file?”
“No,/home/sec it is not a file!”
“But /home/sec/.bash_history is a file!”
./ifnested.sh: line 18: ^d: command not found
```

# Using numeric test comparisons

cat > iftest.sh 
```bash
\#!/bin/bash
val1=10
val2=11
if [ $val1 -gt 5 ]
then
echo “The test value $val1 is greater than 5”
fi
if [ $val1 -eq $val2 ]
then
echo “The values are equal”
else
echo “The values are different”
fi
^d
```


cat iftest.sh 
```bash
\#!/bin/bash
val1=10
val2=11
if [ $val1 -gt 5 ]
then
echo “The test value $val1 is greater than 5”
fi
if [ $val1 -eq $val2 ]
then
echo “The values are equal”
else
echo “The values are different”
fi
```

$ chmod 755 iftest.sh
 
$ ./iftest.sh 

##OUTPUT
```
“The test value 10 is greater than 5”
“The values are different”
./iftest.sh: line 14: ^d: command not found
```

# Check if a file

cat > ifnested.sh 
```bash
\#!/bin/bash
if [ -e $HOME ]
then
echo “$HOME The object exists, is it a file?”
if [ -f $HOME ]
then
echo “Yes,$HOME it is a file!”
else
echo “No,$HOME it is not a file!”
if [ -f $HOME/.bash_history ]
then
echo “But $HOME/.bash_history is a file!”
fi
fi
else
echo “Sorry, the object does not exist”
fi
^d
```

cat ifnested.sh 
```bash
\#!/bin/bash
if [ -e $HOME ]
then
echo “$HOME The object exists, is it a file?”
if [ -f $HOME ]
then
echo “Yes,$HOME it is a file!”
else
echo “No,$HOME it is not a file!”
if [ -f $HOME/.bash_history ]
then
echo “But $HOME/.bash_history is a file!”
fi
fi
else
echo “Sorry, the object does not exist”
fi
```

$ chmod 755 ifnested.sh
 
$ ./ifnested.sh 

##OUTPUT
```
./ifnested.sh: line 1: #!/bin/bash: No such file or directory
“/home/sec The object exists, is it a file?”
“No,/home/sec it is not a file!”
“But /home/sec/.bash_history is a file!”
./ifnested.sh: line 18: ^d: command not found
```

# Looking for a possible value using elif

cat elifcheck.sh 
```bash
\#!/bin/bash
if [ $USER = Ram ]
then
echo "Welcome $USER"
echo "Please enjoy your visit"
elif [ $USER = Rahim ]
then
echo "Welcome $USER"
echo "Please enjoy your visit"
elif [ $USER = Robert ]
then
echo "Special testing account"
elif [ $USER = gganesh ]
then
echo "$USER, Do not forget to logout when you're done"
else
echo "Sorry, you are not allowed here"
fi
```

$ chmod 755 elifcheck.sh
 
$ ./elifcheck.sh 

## OUTPUT
```
./elifcheck.sh: line 1: #!/bin/bash: No such file or directory
Sorry, you are not allowed here
```

# Testing compound comparisons

cat > ifcompound.sh 
```bash
\#!/bin/bash
if [ -d $HOME ] && [ -w $HOME ]
then
echo "The file exists and you can write to it"
else
echo "I cannot write to the file"
fi
```
$ chmod 755 ifcompound.sh

$ ./ifcompound.sh 

## OUTPUT
```
./ifcompound.sh: line 1: #!/bin/bash: No such file or directory
The file exists and you can write to it
```

# Using the case command
cat >casecheck.sh 
```bash
case $USER in
Ram | Robert)
echo "Welcome, $USER"
echo "Please enjoy your visit";;
Rahim)
echo "Special testing account";;
gganesh)
echo "$USER, Do not forget to log off when you're done";;
*)
echo "Sorry, you are not allowed here";;
esac
```
$ chmod 755 casecheck.sh 
 
$ ./casecheck.sh 

# Output

```
Sorry, you are not allowed here
```
 
cat > whiletest
```bash
#!/bin/bash
#while command test
var1=10
while [ $var1 -gt 0 ]
do
echo $var1
var1=$[ $var1 - 1 ]
done
```
$ chmod 755 whiletest.sh
 
$ ./whiletest.sh

# Output
```
10
9
8
7
6
5
4
3
2
1
```
 
cat untiltest.sh 
```bash
\#using the until command
var1=100
until [ $var1 -eq 0 ]
do
echo $var1
var1=$[ $var1 - 25 ]
done
``` 
$ chmod 755 untiltest.sh

$ ./untiltest.sh
 
# Output
```
./untiltest.sh: line 1: #using: command not found
100
75
50
25
```
 
cat forin1.sh 
```bash
\#!/bin/bash
\#basic for command
for test in Alabama Alaska Arizona Arkansas California Colorado
do
echo The next state is $test
done
 ```
 
$ chmod 755 forin1.sh

$ ./forin1.sh
 
# Output
```
./forin1.sh: line 1: #!/bin/bash: No such file or directory
./forin1.sh: line 2: #basic: command not found
The next state is Alabama
The next state is Alaska
The next state is Arizona
The next state is Arkansas
The next state is California
The next state is Colorado
```

cat forin2.sh 
```bash
\#!/bin/bash
\# another example of how not to use the for command
for test in I don't know if this'll work
do
echo “word:$test”
done
 ```
 
$ chmod 755 forin2.sh
 
cat forin2.sh 
```bash
\#!/bin/bash
\# another example of how not to use the for command
for test in I don't know if this'll work
do
echo “word:$test”
done
```
$ chmod 755 forin2.sh
 
$ ./forin2.sh 
 
# Output
```
./forin2.sh: line 1: #!/bin/bash: No such file or directory
./forin2.sh: line 2: #: command not found
“word:I”
“word:dont know if thisll”
“word:work”
```

cat forin3.sh 
```bash
\#!/bin/bash
\# another example of how not to use the for command
for test in I don\'t know if "this'll" work
do
echo "word:$test"
done
```
$ ./forin3.sh 
 
# Output

![alt text](<Screenshot from 2024-02-27 22-15-10.png>)

cat forin1.sh 
```bash
#!/bin/bash
# basic for command
for test in Alabama Alaska Arizona Arkansas California Colorado
do
echo The next state is $test
done
```
$ chmod 755 forin1.sh

./forin1.sh

## OUTPUT
```
The next state is Alabama
The next state is Alaska
The next state is Arizona
The next state is Arkansas
The next state is California
The next state is Colorado
```

cat forinfile.sh 
```bash
#!/bin/bash
# reading values from a file
file="cities"
for state in `cat $file`
do
echo "Visit beautiful $file“
done
```
$ chmod 777 forinfile.sh

$ cat cities
```
Hyderabad
Alampur
Basara
Warangal
Adilabad
Bhadrachalam
Khammam
```

## OUTPUT


cat forctype.sh 
```bash
#!/bin/bash
# testing the C-style for loop
for (( i=1; i <= 5; i++ ))
do
echo "The value of i is $i"
done
````
$ chmod 755 forctype.sh
$ ./forctype.sh 
## OUTPUT

cat forctype1.sh 
```bash
#!/bin/bash
# multiple variables
for (( a=1, b=5; a <= 5; a++, b-- ))
do
echo "$a - $b"
done
```
$ chmod 755 forctype.sh

$ ./forctype1.sh 

## OUTPUT
```
bash: ./forctype1.sh: No such file or directory
```

cat fornested1.sh 
```bash
#!/bin/bash
# nesting for loops
for (( a = 1; a <= 3; a++ ))
do
echo "Starting loop $a:"
for (( b = 1; b <= 3; b++ ))
do
echo " Inside loop: $b"
done
done
```
$ chmod 755 fornested1.sh
 
$ ./fornested1.sh 
## OUTPUT
```
Starting loop 1:
 Inside loop: 1
 Inside loop: 2
 Inside loop: 3
Starting loop 2:
 Inside loop: 1
 Inside loop: 2
 Inside loop: 3
Starting loop 3:
 Inside loop: 1
 Inside loop: 2
 Inside loop: 3
```
 
cat forbreak.sh 
```bash
#!/bin/bash
# breaking out of a for loop
for var1 in 1 2 3 4 5
do
if [ $var1 -eq 3 ]
then
break
fi
echo "Iteration number: $var1"
done
echo "The for loop is completed“
```
$ chmod 755 forbreak.sh
 
$ ./forbreak.sh 
 
cat forbreak.sh 
```bash
#!/bin/bash
# breaking out of a for loop
for var1 in 1 2 3 4 5
do
if [ $var1 -eq 3 ]
then
continue
fi
echo "Iteration number: $var1"
done
echo "The for loop is completed“
```

 
$ chmod 755 forcontinue.sh
 
$ ./forcontinue.sh 
## OUTPUT
```
bash: ./forcontinue.sh: No such file or directory
```
cat exread.sh 
```bash
#!/bin/bash
# testing the read command
echo -n "Enter your name: "
read name
echo "Hello $name, welcome to my program. "
 ```
 
$ chmod 755 exread.sh 
 
$ ./exread.sh 
## OUTPUT
```
Enter your name: Venkatanathan
Hello Venkatanathan, welcome to my program. 
```

cat exread1.sh
```bash
#!/bin/bash
# testing the read command
read -p "Enter your name: " name
echo "Hello $name, welcome to my program. “
``` 
$ chmod 755 exread1.sh 

$ ./exread1.sh 

## OUTPUT
```
Enter your name: Venkatanathan
./exread1.sh: line 4: unexpected EOF while looking for matching `"'
./exread1.sh: line 5: syntax error: unexpected end of file
```

cat funcex.sh
```bash
#!/bin/bash
# trying to access script parameters inside a function
function func {
echo $[ $1 * $2 ]
}
if [ $# -eq 2 ]
then
value=`func $1 $2`
echo "The result is $value"
else
echo "Usage: badtest1 a b"
fi
```
## OUTPUT
 ./funcex.sh 

 ```
 bash: ./funcex.sh: Permission denied
```

 ./funcex.sh 1 2
```
bash: ./funcex.sh: Permission denied
```

cat argshift.sh
```bash
#!/bin/bash 
 while (( "$#" )); do 
  echo $1 
  shift 
done
```
$ chmod 777 argshift.sh

## OUTPUT
$ ./argshift.sh 1 2 3
```
+ ((  3  ))
+ echo 1
1
+ shift
+ ((  2  ))
+ echo 2
2
+ shift
+ ((  1  ))
+ echo 3
3
+ shift
+ ((  0  ))
+ set +x
```

 cat argshift1.sh
```bash
 #/bin/bash 
 # store arguments in a special array 
args=("$@") 
# get number of elements 
ELEMENTS=${#args[@]} 
 # echo each element in array  
# for loop 
for (( i=0;i<$ELEMENTS;i++)); do 
    echo ${args[${i}]} 
done
```
$ chmod 777 argshift.sh

## OUTPUT

$ ./argshift.sh 1 2 3
```
1
2
3

cat argshift.sh
```bash
#!/bin/bash 
set -x 
while (( "$#" )); do 
  echo $1 
  shift 
done
set +x
```
## OUTPUT
 ./argshift.sh 1 2 3
 ```
 + ((  3  ))
+ echo 1
1
+ shift
+ ((  2  ))
+ echo 2
2
+ shift
+ ((  1  ))
+ echo 3
3
+ shift
+ ((  0  ))
+ set +x
```

cat > nc.awk
```bash
BEGIN{}
{
print len=length($0),"\t",$0 
wordcount+=NF
chrcnt+=len
}
END {
print "total characters",chrcnt 
print "Number of Lines are",NR
print "No of Words count:",wordcount
}
 ```
cat>data.dat
```bash
bcdfghj
abcdfghj
bcdfghj
ebcdfghj
bcdfghj
ibcdfghj
bcdfghj
obcdfghj
bcdfghj
ubcdfghj
```
awk -f nc.awk data.dat
## OUTPUT 
```
7 	 bcdfghj
8 	 abcdfghj
7 	 bcdfghj
8 	 ebcdfghj
7 	 bcdfghj
8 	 ibcdfghj
7 	 bcdfghj
8 	 obcdfghj
7 	 bcdfghj
8 	 ubcdfghj
total characters 75
Number of Lines are 10
No of Words count: 10
```

cat > palindrome.sh
```bash
#num=545
echo "Enter the number"
read num
s=0
rev=""
temp=$num
while [ $num -gt 0 ]
do
	# Get Remainder
	s=$(( $num % 10 ))
	# Get next digit
	num=$(( $num / 10 ))
	# Store previous number and
	# current digit in reverse
	rev=$( echo ${rev}${s} )
done
if [ $temp -eq $rev ];
then
	echo "Number is palindrome"
else
	echo "Number is NOT palindrome"
fi
```
chmod 755 palindrome.sh

./palindrome.sh

# OUTPUT 
```
Enter the number
45
Number is NOT palindrome
```

# RESULT:
The Commands are executed successfully.
