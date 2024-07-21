

## Create a debian package for Debian 12, Devuan 5, MX-Linux 23....

For Version 0.8.0 -- "Labyrinth" (19 June 2024) ~/felixfung

The following instruction are for **Debian 12 (Bookworm)** and **Devuan 5 (Daedalus)** and will also work for MX-Linux, Antix, SpiralLinux etc.

It does create the proper but unsigned Debian-Binaries-Packades only. We omit deliberatelly the creation of skippy-xd_x.x.x.orig.tar.gz (debianized source), skippy-xd_x.x.x-x.dsc and skippy-xd_x.x.x-x.debian.tar.xz.

### Befor you do anything:

You need to update and upgrade the system first!!!


### The required tools are:

```
sudo apt-get install build-essential dh-make fakeroot debhelper devscripts pkg-config
```

### The build-depends are:

```
sudo apt-get install libx11-dev libxft-dev libxcomposite-dev libxdamage-dev libxinerama-dev libgdcm-dev libjpeg62-turbo-dev libgif-dev
```

We don't use git, we download the zip-file!

### And now:

Download the zip-file from: <https://github.com/felixfung/skippy-xd> and unzip it, thus creating a directory 'skippy-xd-mster'.

Do not enter 'skippy-xd-master' but download the zip-file from <https://github.com/tonywhatever/deb_build4skippy> and unzip it.

Within the *newly* created directory 'deb_build4skippy-main' do:

```
cp -a /debian ../skippy-xd-master/
```

Now enter the skippy-xd-master directory. After checking if /debian is present and populated with files and a sub-directory execute the next command:

```
dpkg-buildpackage -rfakeroot -us -uc -b
```

and very shortly after you should find two new deb-binaries in the parent-directory of skippy-xd-master. (Any warning about debian/changelog can be safely ignored, it's OK)

You can now install them.
```
sudo gdebi skippy-xd_0.8.0-1_amd64.deb
```
Optional:
```
sudo gdebi skippy-xd-dbgsym_0.8.0-1_amd64.deb

```
After the installation it will be listed using for example 'aptitude' under "Obsolete and Locally Created Packages".


It doesn't get much simpler to create your very own proper debian-package.



Enjoy!

