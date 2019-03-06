---
Type:            article
Title:           Building HandBrake for Linux
Project:         HandBrake
Project_URL:     https://handbrake.fr/
Project_Version: Latest
Language:        English
Language_Code:   en
Authors:         [ Bradley Sepos <bradley@bradleysepos.com> (BradleyS) ]
Copyright:       2019 HandBrake Team
License:         Creative Commons Attribution-ShareAlike 4.0 International
License_Abbr:    CC BY-SA 4.0
License_URL:     https://handbrake.fr/docs/license.html
---

Building HandBrake for Linux
============================

If you have installed a HandBrake package from your distribution or other third-party package repository, please remove it before proceeding. See the section, *Warning about broken third-party builds* on [Where to get HandBrake](../get-handbrake/where-to-get-handbrake.html) for more information.

## Installing dependencies

Dependency installation instructions are available for the following distributions.

- [Arch](install-dependencies-arch.html)
- [CentOS](install-dependencies-centos.html)
- [Debian](install-dependencies-debian.html)
- [Fedora](install-dependencies-fedora.html)
- [Gentoo](install-dependencies-gentoo.html)
- [Ubuntu](install-dependencies-ubuntu.html)

HandBrake's experimental support for Intel Quick Sync Video on Linux requires the [Intel Media SDK](https://github.com/Intel-Media-SDK/MediaSDK/releases).

## Building HandBrake

Clone the HandBrake repository.

    git clone https://github.com/HandBrake/HandBrake.git && cd HandBrake

Build HandBrake. To enable experimental support for Intel QSV via the [Intel Media SDK](https://github.com/Intel-Media-SDK/MediaSDK/releases), append `--enable-qsv`. To build the command line interface only, disable the graphical interface by appending `--disable-gtk`.

    ./configure --launch-jobs=$(nproc) --launch

When complete, you will find `HandBrakeCLI` in the `build` directory. If the graphical interface is enabled, you will also find `ghb` in the `build/gtk/src` directory.

Install HandBrake (optional). When installing the graphical interface, icon and desktop files for the Applications menu will be also installed.

    sudo make --directory=build install

To start over, simply remove the `build` directory.

    rm -rf build

## Building Intel MediaSDK (QSV support only)

For Quick Sync Video support, the Intel MediaSDK and it's dependencies must be built and installed separately.  [Intel MediaSDK Build Instructions](https://github.com/Intel-Media-SDK/MediaSDK#how-to-build), and [Releases](https://github.com/Intel-Media-SDK/MediaSDK/releases) are available on their GitHub repository.  MediaSDK dependencies are listed on the releases page.
