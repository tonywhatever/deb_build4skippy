

## Create a debian package for all flavours of Ubuntu 24.04 LTS and Linux Mint 22 Beta (Codebase: Ubuntu 24.04)

Architecture: amd64

If you use **Ubuntu 22.04/Linux Mint 21** it can easely be backported. See further down.


For Version 0.9.0 -- "Marble" (26 Dec 2024) ~/felixfung


It does create the proper but unsigned Debian-Binaries-Packades only. We omit deliberatelly the creation of skippy-xd_x.x.x.orig.tar.gz (debianized source), skippy-xd_x.x.x-x.dsc and skippy-xd_x.x.x-x.debian.tar.xz.

### Befor you do anything:

You need to update and upgrade the system first!!!


### The required tools are:

```
sudo apt-get install build-essential dh-make fakeroot debhelper devscripts pkg-config
```

### The build-depends are:

```
sudo apt-get install libx11-dev libxft-dev libxcomposite-dev libxdamage-dev libxinerama-dev libgdcm-dev libjpeg-turbo8-dev libgif-dev
```

We don't use git, we download the zip-file!

### And now:

Download the zip-file from: <https://github.com/felixfung/skippy-xd> and unzip it, thus creating a directory 'skippy-xd-mster'.

Do not enter 'skippy-xd-master' but download the zip-file from <https://github.com/tonywhatever/deb_build4skippy> and unzip it.

Within the *newly* created directory 'deb_build4skippy-main' do:

---Start of Backport Instruction

Edit first the File /4ubuntu_only/changelog and replace 'ubuntu24.04' with 'ubuntu22.04' and save the file. That is all!

---End of Backport Instruction

```
cp -a ./debian ../skippy-xd-master/
cp ./4ubunu_only/changelog ../skippy-xd-master/debian/
cp ./4ubunu_only/control ../skippy-xd-master/debian/
cp ./4ubunu_only/ready4ubuntu ../skippy-xd-master/
```

Now enter the skippy-xd-master directory. After checking if /debian is present and populated with files and a sub-directory execute the next command (from ./skippy-xd-master/):

```
dpkg-buildpackage -rfakeroot -us -uc -b
```

and very shortly after you should find two new deb-binaries in the parent-directory of skippy-xd-master. (Any warning about debian/changelog can be safely ignored, it's OK)

You can now install them for example with:
```
sudo gdebi skippy-xd_0.9.0-1~ubuntu24.04_amd64.deb
```
Optional (I have no idea why in Ubuntu the dbgsym-file gets renamed to *.ddeb):
```
sudo gdebi kippy-xd-dbgsym_0.9.0-1~ubuntu24.04_amd64.ddeb
```

After the installation it will be listed using for example 'aptitude' under "Obsolete and Locally Created Packages".

It doesn't get much simpler to create your very own proper debian-package.



Enjoy!

