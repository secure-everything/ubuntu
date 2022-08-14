


#include <tunables/global>


profile /opt/google/chrome/chrome {


  #include <abstractions/fonts>

  #include <abstractions/gnome>
  
  capability sys_admin ,
  capability sys_chroot,
  
  network inet stream,
  network inet6 stream,
  network inet dgram,
  network inet6 dgram,
  network inet seqpacket,
  network inet6 seqpacket,


  /etc/udev/udev.conf r,
  /etc/localtime      r,
  /etc/machine-id     r,
  /etc/os-release     r,
  /etc/fonts/**       r,
  /etc/gtk-3.0/settings.ini   r,
  
/lib/x86_64-linux-gnu/libdl.so.2                 mr,
/lib/x86_64-linux-gnu/libpthread.so.0            mr,
/lib/x86_64-linux-gnu/libgobject-2.0.so.0        mr,
/lib/x86_64-linux-gnu/libnss3.so                 mr,
/lib/x86_64-linux-gnu/libnssutil3.so             mr,
/lib/x86_64-linux-gnu/libsmime3.so               mr,
/lib/x86_64-linux-gnu/libnspr4.so                mr,
/lib/x86_64-linux-gnu/libatk-1.0.so.0            mr,
/lib/x86_64-linux-gnu/libatk-bridge-2.0.so.0     mr,
/lib/x86_64-linux-gnu/libgio-2.0.so.0            mr,
/lib/x86_64-linux-gnu/libdrm.so.2                mr,
/lib/x86_64-linux-gnu/libdbus-1.so.3             mr,
/lib/x86_64-linux-gnu/libexpat.so.1              mr,
/lib/x86_64-linux-gnu/libm.so.6                  mr,
/lib/x86_64-linux-gnu/libX11.so.6                mr,
/lib/x86_64-linux-gnu/libXcomposite.so.1         mr,
/lib/x86_64-linux-gnu/libXdamage.so.1            mr,
/lib/x86_64-linux-gnu/libXext.so.6               mr,
/lib/x86_64-linux-gnu/libXfixes.so.3             mr,
/lib/x86_64-linux-gnu/libXrandr.so.2             mr,
/lib/x86_64-linux-gnu/libgbm.so.1                mr,
/lib/x86_64-linux-gnu/libxcb.so.1                mr,
/lib/x86_64-linux-gnu/libxkbcommon.so.0          mr,
/lib/x86_64-linux-gnu/libpango-1.0.so.0          mr,
/lib/x86_64-linux-gnu/libcairo.so.2              mr,
/lib/x86_64-linux-gnu/libasound.so.2             mr,
/lib/x86_64-linux-gnu/libatspi.so.0              mr,
/lib/x86_64-linux-gnu/libgcc_s.so.1              mr,
/lib/x86_64-linux-gnu/libc.so.6                  mr,
/lib/x86_64-linux-gnu/libffi.so.8                mr,
/lib/x86_64-linux-gnu/libpcre.so.3               mr,
/lib/x86_64-linux-gnu/libplc4.so                 mr,
/lib/x86_64-linux-gnu/libplds4.so                mr,
/lib/x86_64-linux-gnu/libgssapi_krb5.so.2        mr,
/lib/x86_64-linux-gnu/libavahi-common.so.3       mr,
/lib/x86_64-linux-gnu/libavahi-client.so.3       mr,
/lib/x86_64-linux-gnu/libgnutls.so.30            mr,
/lib/x86_64-linux-gnu/libz.so.1                  mr,
/lib/x86_64-linux-gnu/libgmodule-2.0.so.0        mr,
/lib/x86_64-linux-gnu/libmount.so.1              mr,
/lib/x86_64-linux-gnu/libselinux.so.1            mr,
/lib/x86_64-linux-gnu/libsystemd.so.0            mr,
/lib/x86_64-linux-gnu/libXrender.so.1            mr,
/lib/x86_64-linux-gnu/libwayland-server.so.0     mr,
/lib/x86_64-linux-gnu/libstdc++.so.6             mr,
/lib/x86_64-linux-gnu/libXau.so.6                mr,
/lib/x86_64-linux-gnu/libXdmcp.so.6              mr,
/lib/x86_64-linux-gnu/libfribidi.so.0            mr,
/lib/x86_64-linux-gnu/libthai.so.0               mr,
/lib/x86_64-linux-gnu/libharfbuzz.so.0           mr,
/lib/x86_64-linux-gnu/libpixman-1.so.0           mr,
/lib/x86_64-linux-gnu/libfontconfig.so.1         mr,
/lib/x86_64-linux-gnu/libfreetype.so.6           mr,
/lib/x86_64-linux-gnu/libpng16.so.16             mr,
/lib/x86_64-linux-gnu/libxcb-shm.so.0            mr,
/lib/x86_64-linux-gnu/libxcb-render.so.0         mr,
/lib/x86_64-linux-gnu/libXi.so.6                 mr,
/lib/x86_64-linux-gnu/libkrb5.so.3               mr,
/lib/x86_64-linux-gnu/libk5crypto.so.3           mr,
/lib/x86_64-linux-gnu/libcom_err.so.2            mr,
/lib/x86_64-linux-gnu/libkrb5support.so.0        mr,
/lib/x86_64-linux-gnu/libp11-kit.so.0            mr,
/lib/x86_64-linux-gnu/libidn2.so.0               mr,
/lib/x86_64-linux-gnu/libunistring.so.2          mr,
/lib/x86_64-linux-gnu/libtasn1.so.6              mr,
/lib/x86_64-linux-gnu/libnettle.so.8             mr,
/lib/x86_64-linux-gnu/libhogweed.so.6            mr,
/lib/x86_64-linux-gnu/libblkid.so.1              mr,
/lib/x86_64-linux-gnu/libgmp.so.10               mr,
/lib/x86_64-linux-gnu/libpcre2-8.so.0            mr,
/lib/x86_64-linux-gnu/liblzma.so.5               mr,
/lib/x86_64-linux-gnu/libzstd.so.1               mr,
/lib/x86_64-linux-gnu/liblz4.so.1                mr,
/lib/x86_64-linux-gnu/libcap.so.2                mr,
/lib/x86_64-linux-gnu/libgcrypt.so.20            mr,
/lib/x86_64-linux-gnu/libbsd.so.0                mr,
/lib/x86_64-linux-gnu/libdatrie.so.1             mr,
/lib/x86_64-linux-gnu/libgraphite2.so.3          mr,
/lib/x86_64-linux-gnu/libuuid.so.1               mr,
/lib/x86_64-linux-gnu/libbrotlidec.so.1          mr,
/lib/x86_64-linux-gnu/libkeyutils.so.1           mr,
/lib/x86_64-linux-gnu/libresolv.so.2             mr,
/lib/x86_64-linux-gnu/libgpg-error.so.0          mr,
/lib/x86_64-linux-gnu/libmd.so.0                 mr,
/lib/x86_64-linux-gnu/libgtk-3.so.0              mr,
/lib/x86_64-linux-gnu/libpangocairo-1.0.so.0     mr,
/lib/x86_64-linux-gnu/libcairo-gobject.so.2      mr,
/lib/x86_64-linux-gnu/libgdk_pixbuf-2.0.so.0     mr,
/lib/x86_64-linux-gnu/libepoxy.so.0              mr,
/lib/x86_64-linux-gnu/libpangoft2-1.0.so.0       mr,
/lib/x86_64-linux-gnu/libXinerama.so.1           mr,
/lib/x86_64-linux-gnu/libXcursor.so.1            mr,
/lib/x86_64-linux-gnu/libwayland-cursor.so.0     mr,
/lib/x86_64-linux-gnu/libwayland-egl.so.1        mr,
/lib/x86_64-linux-gnu/libwayland-client.so.0     mr,
/lib/x86_64-linux-gnu/libjpeg.so.8               mr,
/lib/x86_64-linux-gnu/libX11-xcb.so.1            mr,
/lib/x86_64-linux-gnu/libsecret-1.so.0           mr,
/lib/x86_64-linux-gnu/libcanberra-gtk3.so.0      mr,
/lib/x86_64-linux-gnu/libcanberra.so.0           mr,
/lib/x86_64-linux-gnu/libvorbisfile.so.3         mr,
/lib/x86_64-linux-gnu/libtdb.so.1                mr,
/lib/x86_64-linux-gnu/libltdl.so.7               mr,
/lib/x86_64-linux-gnu/libvorbis.so.0             mr,
/lib/x86_64-linux-gnu/libogg.so.0                mr,
/lib/x86_64-linux-gnu/librsvg-2.so.2             mr,
/lib/x86_64-linux-gnu/libxml2.so.2               mr,
/lib/x86_64-linux-gnu/libicuuc.so.70             mr,
/lib/x86_64-linux-gnu/libicudata.so.70           mr,
/lib/x86_64-linux-gnu/libibus-1.0.so.5           mr,
  
  /lib64/**               mr,

  /opt/google/chrome/**         mrix,

  owner /run/user/[0-9]*/.mutter-Xwaylandauth.*    r,
    
  /usr/share/locale         r,
  /usr/share/zoneinfo/**    r,
  /usr/share/fontconfig/**  r,
  /usr/share/fonts/**       r,
  /usr/share/icons/**       r,
  /usr/share/locale-langpack/**  r,
  /usr/share/pixmaps/**     r,
  /usr/share/ubuntu/**      r,
  /usr/share/themes/**      r,
  /usr/share/X11/**         r, 
  /usr/share/glib-2.0/**    r,
  /usr/share/dconf/**       r,
  /usr/share/mime.**        r,
  /usr/share/mime/**        r,
  /usr/local/share/**       r,

/usr/lib/x86_64-linux-gnu/gconv/gconv-modules.cache                     mr,
/usr/lib/x86_64-linux-gnu/gio/modules                                   mr,
/usr/lib/x86_64-linux-gnu/gio/modules/giomodule.cache                   mr,
/usr/lib/x86_64-linux-gnu/gio/modules/libgvfsdbus.so                    mr,
/usr/lib/x86_64-linux-gnu/gio/modules/libgioremote-volume-monitor.so    mr,
/usr/lib/x86_64-linux-gnu/gio/modules/libgiognutls.so                   mr,
/usr/lib/x86_64-linux-gnu/gio/modules/libgiolibproxy.so                 mr,
/usr/lib/x86_64-linux-gnu/gio/modules/libgiognomeproxy.so               mr,
/usr/lib/x86_64-linux-gnu/gio/modules/libgioenvironmentproxy.so         mr,
/usr/lib/x86_64-linux-gnu/gio/modules/libdconfsettings.so               mr,
/usr/lib/x86_64-linux-gnu/gio/modules/libgvfsdbus.so                    mr,
/usr/lib/x86_64-linux-gnu/gvfs/glibc-hwcaps/x86-64-v3/libgvfscommon.so  mr,
/usr/lib/x86_64-linux-gnu/gvfs/libgvfscommon.so                         mr,
/usr/lib/x86_64-linux-gnu/gvfs/modules                                  mr,
/usr/lib/x86_64-linux-gnu/gdk-pixbuf-2.0/2.10.0/loaders.cache           mr,
/usr/lib/x86_64-linux-gnu/gtk-3.0/modules/libcanberra-gtk-module.so     mr,
/usr/lib/x86_64-linux-gnu/gdk-pixbuf-2.0/2.10.0/loaders/libpixbufloader-svg.so     mr,
/usr/lib/x86_64-linux-gnu/gtk-3.0/3.0.0/immodules.cache                 mr,
/usr/lib/x86_64-linux-gnu/gtk-3.0/3.0.0/immodules/im-ibus.so            mr, 

  /usr/lib/locale/locale-archive                  r,
  /usr/lib/os-release       r,
  
  /sys/devices/system/cpu                                   r,

  /tmp/.com.google.Chrome.*/ rw,
  /tmp/.com.google.Chrome.*/Singleton* rw,  
  
  /dev/shm/.com.google*           rw,  

  /proc/                          r,
  /proc/[0-9]*/cmdline r,
  /proc/[0-9]*/fd/ r,
  /proc/[0-9]*/stat r,
  /proc/[0-9]*/statm r,
  /proc/[0-9]*/status r,
  /proc/cpuinfo r,
  /proc/sys/kernel/yama/ptrace_scope r,
  
  /var/tmp/ r,
  /var/tmp/* rw,
  
  owner @{HOME}/Downloads/**               rw,
  owner @{HOME}/.config/google-chrome/**   rwk,
  owner @{HOME}/.config/ibus/bus           rw,
  owner @{HOME}/.cache/google-chrome/Default/**       rw,
  
  
}


----------------------------------------------------------------------------------------------------------------
Minimal apparmor profile for Chrome on Ubuntu 22.04. File contains all that's necessary to run Chrome. It does not have any mention of /bin or /sbin programs. And does not give blanket read rights to /tmp, /run, /dev, /sys. /etc, /home/yourAccount/Documents directories. It was developed by carefully inspecting strace output. Even if hackers manage to compromise Chrome, they would not be able to do anything useful.

Which brings me to firejail. It is a virtualization security app. Which run it's protected apps in a virtual environment. Firejail claims to protect 1000 common apps. ( I haven't counted their config files in /etc/firejail )

Apparmor job is to protect an app by only allowing specified modules and file read and writes to only the select few specified things. If an attacker manages to use only the specified few things to accomplish his hack, then apparmor cannot protect us any further. Virtualization comes in and provides a virtual environment to run the app in. And wipes away the environment after use and ensures that nothing of a hack remains, like for example, a rootkit.

You can never be 100% certain that your apps do not harbour any security vulnerabilities. And hackers know these and pass them around. White hat hackers would report security vulnerabilities and create a CVS report so that the app developers can fix them. But black hat hackers far out number white hats. White hats can earn serious money by reporting vulnerabilities and yet black hat hackers still persist. But black hats can maybe earn more by blackmailing people with ransomware. And by the way, the apparmor profile above only allows writes to the Downloads folder, so your Documents folder is safe. Be aware also that the default snap packaged Firefox apparmor profile allows reads and writes to the ENTIRE home folder - I wouldn't use that if I were you.

Firejail is easy to use. Just install firejail and run 'sudo firecfg'. It creates some .desktop files under 'home/yourAccount/.local/share/applications. These are your protected applications and they show up in the 'Show Applications' 9 dot icon.

You can modify these .desktop files to add more security features of firejail. Just sudo gedit a .desktop file and look for the Exec line. Then add options between the word 'firejail' and the part that starts the app.

For example mine has this portion added: '--ignore=private-dev --caps.drop=all --machine-id --net=enp1s0 --dns=9.9.9.9 --netfilter=/etc/firejail/nolocal.net ' . This portion specifies that it should create a virtual network 'card' with a temporary ip address. And that ip address changes every time you start your app. It also has an '--ignore=private dev' so I can use my usb Yubikey hardware token to sign on to facebook and email.
If you are not using Ubuntu, you should change 'enp1s0' to 'eth0'.

BTW, Yubikeys are the definitive 2nd factor authentication method. Costs $25. More secure than a cell phone app, as cell phones can be hacked, especially Andriods.
