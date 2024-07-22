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

The container (holding 2 debs) by the name of **Debian12-skippy-xd_0.8.0-2_amd64_binaries.tar.gz** is on my 'Google Drive'. You don't have to sign in. The link for downloding is: <https://drive.google.com/file/d/1eNo3ZV5Gsh_oCZYq1oFlfgwwzaP1sArd/view?usp=sharing>

**Please check the integrity** of "Debian12-skippy-xd_0.8.0-2_amd64_binaries.tar.gz"

md5sums: eaed454fbb0ae56f2fa85e40746ec9f4

sha256sums: 6ce0ad7d6f08b569a50f445ae779e6a63330e5d56af0ac2edd0a6552d91682ee 

.

**For Ubuntu 24.04 LTS and Linux Mint 22 Beta (Codebase: Ubuntu 24.04)**

The container (holding 2 debs) by the name of **Ubuntu24.04-skippy-xd_0.8.0-1_amd64_binaries.tar.gz** is on my 'Google Drive'. You don't have to sign in. The link for downloding is: <https://drive.google.com/file/d/1FJ3UHk-sMF7MOFcdN5G9rLQpZTj2IYUj/view?usp=drive_link>

**Please check the integrity** of "Ubuntu24.04-skippy-xd_0.8.0-1_amd64_binaries.tar.gz"

md5sums: 8f8e84236cd6a811fe82396fd70ecac3

sha256sums: d675027aaa2d252d604fc61bd728ce3f4acc15c408433a71b85add9d8491ee33

.



## How to create a skippy-xd debian package?

No need to panic, no editing required (except for backporting and that is for changing one word only). After downloading the essential tools, the build-dependencies and the 2 zip-files you will have an installable debian-package within a few minutes. It is as easy as that.

For Debian read Debian-Recipe.md

For Ubuntu and Linux Mint (includes backporting) read Ubuntu-Recipe.md



Enjoy!

