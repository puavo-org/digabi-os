Digabi OS (DOS)
================================
TL;DR Sources for Digabi OS, a Live-Linux system, created by The 
Matriculation Examination Board of Finland (In Finnish: 
[Ylioppilastutkintolautakunta](http://www.ylioppilastutkinto.fi/)).


## Goals
Live system goals:

 * prevent cheating (using forbidden materials, communication w/ other 
  students, using internet when forbidden)
 * provide solid system for attending the exam


## Documentation
For documentation, see `doc/*.md`. Manual for `live-build` toolset: 
[Debian Live Manual](http://live.debian.net/manual/3.x/).

### Requirements for build system
 * [Debian](http://www.debian.org/) 8.0 (jessie)
 * for required packages, see file 
 `custom-packages/digabi-dev/debian/control` (especially lines Depends, 
 Recommends)
 * you may use [Digabi Buildbox](http://sourceforge.net/projects/digabi/files/tools), VirtualBox machine image for build environment. You probably want to run `sudo apt-get update && sudo apt-get dist-upgrade` after first run


### How to build
Assuming you have required packages installed (see above), building new 
image is quite easy:

Our official images are published via [SourceForge](http://sourceforge.net/projects/digabi/files/).

## New
New build system (copied from [Tails](https://tails.boum.org/)) uses Ruby Rake for running tasks. To build new image, run

    git clone https://github.com/digabi/digabi-os.git
    cd digabi-live
    rake build ; rake vm:halt

After build you can find image in current directory (`digabi-*.iso`).

Run `rake -T` if you want to see available tasks.


## Old

    git clone https://github.com/digabi/digabi-os.git digabi-os
    cd digabi-os
    git submodule init && git submodule update
    make dist

After building, image can be found in `dist/` directory.


## Disclaimer
The current version of the Matriculation Examination Board's exam 
operating system aims to demonstrate the exam execution environment. 
The Matriculation Examination Board reserves the right to revise the 
exam operating system without prior notice.  As this is solely a test 
version, the final product may be different.

The operating system is designed so that it will not make modifications 
to the workstation. All testing is done at one's own risk.


## License
This product is based on upcoming Debian 8.0 (jessie), and includes 
software w/ various licenses. For licensing information, see [Debian 
License information ](http://www.debian.org/legal/licenses/). Work done 
by MEB is licensed under GPLv3, except MEB/Digabi logos (included in 
some `digabi-*` packages), and when otherwise noted.


## Contact
 * [The Matriculation Examination Board of Finland](http://www.ylioppilastutkinto.fi/), PB50, 00581 Helsinki, Finland
 * Project website: [digabi.fi](http://digabi.fi/)
 * [github.com/digabi/digabi-live](https://github.com/digabi/digabi-os)
 * email: [digabi@ylioppilastutkinto.fi](mailto:digabi@ylioppilastutkinto.fi)
