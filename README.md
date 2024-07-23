# Updating it. Do not use it, will be usable again on Tue 23 Jul 2024 21:33:26 NZST


# deb_build4skippy 

Architecture: amd64

Preliminary:

Thanks to *Felix Fung* skippy-xd is not dead. The project's URL is: <https://github.com/felixfung/skippy-xd>/

Please note the following:

I am not an official debian-packager nor a coder and using Git is a pain in the neck for me. However I think that my very own two deb-pkgs are more up to date and far more debian-conforming in contrast to the available packages from the usual debian repos.

Goal:

My aim is to support Felix Fung's project with a proper debian-tree for the folks who want to create their own two debian binary packages to run skippy-xd.

Installable unsigned *'Debian Bookworm (12)-amd64'* , *'Ubuntu Noble (24.04)-amd64'* packages are made available for downloading.

## Where are the binary packages for downloading?

**For Debian 12**

The container (holding 2 debs) is on my 'Google Drive'. You don't have to sign in. The link for downloding is: <https://drive.google.com/file/d/1s3yCILDDnvUDKHhAZTaBjAhzzUYocao_/view?usp=drive_link>

**Please check the integrity** of "Debian12-skippy-xd_0.8.0-2_amd64_binaries.tar.gz"

md5sums: 6e41e41997e28d6c36e8a4eaabd60783

sha256sums: d66fe92e3f67d6ead64d7cab8feea886112c4460f485c5835ff1fd926b06e147

.

**For Ubuntu 24.04 LTS and Linux Mint 22 Beta (Codebase: Ubuntu 24.04)**

The container (holding 2 debs) is on my 'Google Drive'. You don't have to sign in. The link for downloding is: <https://drive.google.com/file/d/1l3r6AL6Q96-EsFr7XwlP7fTjxXLMueBd/view?usp=drive_link>

**Please check the integrity** of "Ubuntu24.04-skippy-xd_0.8.0-2_amd64_binaries.tar.gz"

md5sums: d863b7466c4a0ee19dcd7e6b74a9b1ff

sha256sums: 2a3a4c82759b239a1fb73f3c59b73b448a749b59c7acb23cc1094a1518619ea4

.

**For Ubuntu 22.04 LTS and Linux Mint 21**

The container (holding 2 debs) is on my 'Google Drive'. You don't have to sign in. The link for downloding is: <https://drive.google.com/file/d/14Hm1fJqqop8caBL49hdI4idxeYzpOrki/view?usp=drive_link>

**Please check the integrity** of "Ubuntu22.04-skippy-xd_0.8.0-2_amd64_binaries.tar.gz"

md5sums: 4a8fe08cc32db42240c98f461a484457

sha256sums: 663231d0705088cf6442d5c3493d07a1cf23e624dedc1cc1885b69fd14802e39


.


## How to create a skippy-xd debian package?

No need to panic, no editing required (except for backporting and that is for changing one word only). After downloading the essential tools, the build-dependencies and the 2 zip-files you will have an installable debian-package within a few minutes. It is as easy as that.

For Debian read Debian-Recipe.md

For Ubuntu and Linux Mint (includes backporting) read Ubuntu-Recipe.md



Enjoy!

