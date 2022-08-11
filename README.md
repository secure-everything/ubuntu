OK, here is the apparmor profile for Chrome Version 104.0.5112.79 on Ubuntu 22.04 LTS Jammy Jellyfish. 2022-08-11. 

It started off from the version found at https://gist.github.com/mauron85/6b6d346b2fbd8dc9070711679546bfda which was coded by https://github.com/detrout/apparmor-det/. That code was from 2016 and doesn't work with the current Chrome and current Ubuntu.

This version's credit belong to https://hardenwindows11forsecurity.com .

---------------------------------------------------------------------------------------------------------------
#include <tunables/global>


profile /opt/google/chrome/chrome {


  #include <abstractions/fonts>
  #include <abstractions/gnome>
 
  network inet  stream,
  network inet6 stream,
  network inet  dgram,
  network inet6 dgram,
  network inet  seqpacket, 
  network inet6 seqpacket, 
 
  capability sys_chroot,

  # /etc/ld.so.cache    r,
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
 
  /lib64/**                   r,
  
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
  
  /dev/shm/.com.google*              rw,  

  /proc/filesystems                   r,
  /proc/self/stat                     r,
  /proc/stat                          r,
  /proc/self/exe                      r,
  /proc/self/cmdline                  r,
  /proc/sys/kernel/yama/ptrace_scope  r,
  /proc/@{pid}/oom_score_adj          w,
  /proc/@{pid}/stat                   r,
  /proc/@{pid}/status                 r,
  /proc/@{pid}/statm                  r,
  
  # HERE HERE NEW var files from strace
  /var/cache/fontconfig/**            r,                    
  /var/lib/dbus/machine-id            r,

  owner @{HOME}/Downloads/**               rw,
  owner @{HOME}/.config/google-chrome/**   rwk,
  owner @{HOME}/.config/ibus/bus           rw,
  owner @{HOME}/.cache/google-chrome/Default/**       rw,
  
}

----------------------------------------------------------------------------------------------------------------

It is not truely minimal, as I didn't list out all of the used libraries. But it doesn't allow /bin and /sbin executables (which are actually links to /usr/bin and /usr/sbin in Ubuntu). Chrome doesn't seem to use any. And it only allows specific reads to /dev, /sys, /run, and /etc folders, not blanket allow-all reads. 

To develop an apparmor profile you first do "strace /opt/google/chrome/chrome 2>output.txt" to run Chrome under strace, and browse to a few sites and stop and close it. The 2> will pipe the output to the file output.txt. Then search through the output file with gedit and CTRL-F search for "open" statements. This gives you all the files the program needs to use. There would be hundreds of these and you need patience. 

Note at the end of each line where it might say "file not found". You don't need to include those; because Chrome is made to work with several distro's and will try to open files at different directories specific to each distro until it finds what it needs. 

Also in each line that says 'open', it will say read only (O_RDONLY) or read-write (O_RDWR). You put r for read only and rw for read-write. A library file needs rights to read, so a 'r' would suffice; it doesn't need execute (ix) . A configuration file at, lets say, home/yourAccount/.config/google-chrome ... needs rw, because the program is writing configuration files to that directory, like a bookmark, or a Chrome setting. 

Usually, only one or two main program files in the program directory needs execute rights (ix).

Then you include some apparmor definitions from /etc/apparmor.d/abstractions and /etc/apparmor.d/tunables. They go like this: #include <abstractions/gnome>. You don't need a lot of these found in the abstraction libraries folder and tunables library folder. Remember, an apparmor profile should be minimalistic, or else you will allow the attacker to do a lot of things. An attacker has all the access that you write into your profile. So make sure you don't give away too many rights. 

Now you go through the list that you have made and eliminate the non-essential things. Not all features designed into a program are essential. For example Linux has dconf, sort of a Windows Registry thing to store settings and things. Most programs including Chrome already stores what it needs into a directory under your home account: home/yourAccount/.config/google-chrome ... . That is a tradition of Unix. So dconf is not necessary, at least in my view. Another one is DBUS; which is for inter-program communication. I don't need Chrome to talk to anything. Last thing I need is some attacker controlled program to send it a shutdown now message or a message to ask what site I am surfing to. System designers are stupid; they dream of this co-operative world where programs talk to each other and provide helpful features. "Oh you are surfing to Youtube, let me start this other helpful program for you". When in fact the user is only concentrating on the program at hand - Chrome, don't expect interuptions, and only an attacker is interested in asking Chrome to do this that and the other, apart from what the Chrome user is actively requesting on the program's own screen. 

Looking at my code I noticed that I specified 'network,' which allows every type of networking there is. And it includes the 'raw' type. And raw is not for videos either, there is a 'stream' type which should be for video streaming. So I now I list only the networking components needed.

Then I noticed I have previously specified 'ptrace', and capability 'sys_ptrace', which are required to use chrome_crashpad_handler.(if you look in chrome's folder you will find it)  I think that's because crashpad can backtrace chrome's code to find out which line caused the crash. Now that is only useful to Google. There is nothing that the crashpad can do to help me get out of a crash - you need to restart the program. So out the door ptrace goes. I don't need helpful debuggers pointing out where the code crashed to hackers. 

Then I noticed that ld.so.cache is readable. So if I ran a program yesterday which used such and such a library, it would be stored there in the cache and will speed up loading things when I start yesterday's program again. Well I only want what chrome actively needs. I don't want to accidentally supply a hacker with code libraries that he might need. So out that goes. 


Now on the top line of the file you wrote, write '/opt/google/chrome/chrome {' and at the last line put a closing brace }. 

Then you name the file opt.google.chrome.chrome, which is substituting every slash (/) for a dot (.).

Copy the file to /etc/apparmor.d . Then run 'apparmor_parser -r /etc/apparmor.d/opt.google.chrome.chrome'. This activates the profile. Or if it fails it tells you of any errors in the file.

Now you may have missed elimnating non-essential features of Chrome. An apparmor profile is meant to allow necessary features. It should be made to be minimal, but sometimes we miss things. Go browse for firejail. Do 'apt install firejail.xxx.deb'. Then run 'firecfg'. which creates firejail profiles of your installed apps. This is a security program for Linux and is meant to sandbox a program so that it doesn't corrupt the system if you get hacked. By corrupt I mean for example a hacker installing a rootkit. It is based on Linux virtualization features, and give a protected program a virtualized view of the system. After a program closes, it wipes that environment away, and nothing it left but a pristine OS. Firejail installs a .desktop file into /home/yourAccount/.local/share/applications directory. And that should automatically show up in the Show Applications nine-dots screen. 

Firejail virtualization is necessary because the programs under it's protection, like Chrome, may have security vulnerabilities known only to hackers. If a vulnerability exists, then a hacker can send Chrome a specially crafted page and obtain rights to run their malware. Ordinarily you have to surf to that page on the inet, but that page could also be sent directly to you by the hacker. You say 'but how does the hacker know my ip address?'. If you are under attack, the hacker already knows a little about you, like what sites you like to surf to. Then they hack that site, and obtain your ip by what your web browser submits to the site. Not a really difficult thing to do, considering that many web sites don't take security precautions. (Thats why you see so many news about leaked credit card accounts. Only massive leaks get to the news, and small intrusions are not reported as per the law.) 

Firejail has a protection feature that changes your ip every time you start a protected program. What you do is edit the Chrome .desktop file in /home/yourAccount/.local/share/applications. CTRL-F to search for the lines that say "Exec". After the word 'firejail', and before the '/opt/google/chrome/chrome', you add these program options: 

 --ignore=private-dev --caps.drop=all --machine-id --net=enp1s0  --dns=9.9.9.9 --netfilter=/etc/firejail/nolocal.net  

This line is made for Ubuntu, and the --net=enp1s0 should be changed to --net=eth0 for other non Debian based distro's. 

The key thing to do in security is to have several 'layers' of security. If one layer fails, you should have another layer. Apparmor could only do so much. It is meant only to restrict what a program can use and do. Under strictly written profiles, it limits what an attacker could run. But if the attacker runs what is within those limits, then there's little that the profile can accomplish. That's why you need firejail. 
