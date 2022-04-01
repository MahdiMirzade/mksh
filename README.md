[mksh(1)](htman/i386/man1/mksh.htm) R59c
----------------------------------------

This is the website of the MirBSD™ Korn Shell, an actively developed free implementation of the Korn Shell programming language and a successor to the Public Domain Korn Shell (pdksh).

This page is always accessible via a redirection at [http://mirbsd.de/mksh](http://mirbsd.de/mksh), which is the canonical homepage URI. There also is (most of the time) [mksh on Freshmeat](http://freecode.com/projects/mksh) and an [mksh project page on ohlol](https://www.ohloh.net/p/mksh), a statistics site. mksh is [experimentally tracked at Launchpad](https://launchpad.net/mksh). Download the Logo as [SVG](pics/mksh.svg) if you want. There’s also a [full licence terms](TaC-mksh.txt) overview; it suffices to say mksh is [Ⓕ Copyfree](http://copyfree.org/) licenced.

 mksh _must_ always be written either “mksh” (all-lowercase) or “MirBSD Korn Shell” — there is no other spelling. It’s usually pronounced by spelling out the four letters m, k, s and h individually, or by saying “MirBSD Korn Shell”.

 Introduction
 ------------

 The current version of mksh is **mksh R59c** from _31 October 2020_.

 Thanks to “Der Verein [trash.net](http://www.trash.net/verein/)” for sponsoring access to a Solaris 8 box. Thanks to Julian “yofuh” Wiesener for just another account on a Sun E420 on Solaris 11β. Thanks to someone who prefers to stay anonymous due to tons of red tape for providing access to an AIX 5.3 system with gcc and xlC installed. (Both are now defunct.) Thanks to Jupp “cnuke” Söntgen for building on AIX in Dresden nowadays. Thanks to HP TestDrive/PvP/DSPP/CLOE, which helps in keeping mksh portable to several Unixes and compilers, and track down some architecture- or glibc-specific bugs. (These days, HP-UX/IA64 only, though.) Thanks to gnubber’s admin (Barry “bddebian” deFreese), as well as Samuel “youpi” Thibault, for providing shell access to a Debian GNU/Hurd system. Thanks to Lucas “laffer1” Holt for ssh access to the MidnightBSD server. Thanks to Waldemar “wbx” Brodkorb for dropping his unused Zaurus SL-C3200 to someone who can actually make use of it to test mksh on OpenBSD. Thanks to Andreas “gecko2” Gockel for access to a couple of Debian and Macintosh boxen and an iPhone 3G. Thanks to Martin Zobel-Helas for an account on an Alpha system. Thanks to Bastian “waldi” Blank for access to an S/390 system and uploading mksh packages to Debian for quite some time. Also thanks to Otavio Salvador and Patrick “aptituz” Schönfeld for uploading a couple of my Debian packages. The Debian GNU/k\*BSD and Hurd developers were quite helpful in assisting and testing as well. Thanks to Thomas E. “TGEN” Spanjaard for access to both a NetBSD and a DragonFly system. Thanks to Josef “jupp” / “penpen” Schugt for testing mksh on a Digital Unix (OSF/1 V4.0) system from the Uni Bonn Physik CIP Pool. Thanks to DEChengst from #UnixNL for providing access to a HP/Compaq Tru64 (OSF/1 V5.1B) system, an OSF/1 V2.0 system and an Ultrix 4.5 system. Thanks to Adam “replaced” Hoka for a BSDi BSD/OS 3.1 ISO9660 image and offering to help with HP-sUX testing (now that HP TestDrive went down) and initial porting to Haiku, which was continued at CLT 2010 with help from Stephan Aßmus. Thanks to André “naaina” Wösten for ssh on a QNX box. Thanks to Olivier Duchateau for testing on Slackware and Zenwalk GNU/Linux. Thanks to Winston W. for spotting musl, and thanks to maximilian attems and H. Peter Anvin for almost fixing klibc. Thanks to RT|Chatzilla, Chris “ir0nh34d” Sutcliffe, and others for Win32 platform assistance. Thanks to KO Myung-Hun for the OS/2 port. Thanks to Daniel Richard G. <skunk@iSKUNK.ORG> for the z/OS (OS/390) initial porting effort and continued testing. Thanks to all other contributors from IRC and the mailing list, including, but not limited to, those already named and Martijn Dekker, Jean Delvare, izabera, J�rg Schilling, carstenh, jilles from FreeBSD, arekm, Torsten Sillke, slagtc, Stéphane Chazelas, colona, zacts, Seb, Steffen Nurpmeso (sdaoden), Dan Douglas (ormaaj), Dr. Werner Fink, … (in no particular order). Thanks to Brian Callahan from the Rensselaer Polytechnic Institute for bug fixes as well as running test builds on AIX 5.1L with the xlC 5.0.2.0 and gcc-2.9, and on Solaris 8 with Forte Developer 7 C 5.4 and gcc 2.95.2 and 3.4.6 compilers. Thanks Stanley J. Johnson and the MirBSD southern hemisphere manager Finn Thain, who made the A/UX port possible. No thanks to Intel for not including mksh in their programme analysing code. (Did I miss anyone? Mail me if so. Some of these are past, anyway.)

 What is [mksh(1)](htman/i386/man1/mksh.htm)? — Short answer: The MirBSD Korn Shell. Okay, but what exactly does it do, or why another shell? These questions will be answered [here](mksh_old.htm#contrib) for the people interested. Right now, you only need to know that mksh is a [DFSG](http://www.debian.org/social_contract#guidelines)\-free and [OSD](http://www.opensource.org/docs/osd)\-compliant (and OSI approved) successor to pdksh, developed as part of [the MirOS Project](http://mirbsd.de/) as native Bourne/POSIX/Korn shell for MirOS BSD, but also to be readily available under other UNIX®-like operating systems.

 The source code for mksh is available at the MirOS Project mirrors as well as these of other operating system projects due to being [included](#otheros) in these; however, we do not provide binaries. Find [instructions to build and install mksh](#build) below, or ask your operating environment vendor to package and include mksh; we provide assistance for this task if asked. _Licencing_ permits this as long as due credit is given to the authors and contributors and the copyright notices are not removed in their entirety; modifying is allowed (but if the result is still called mksh, it’s discouraged; talk with us if you feel you have to modify mksh). The individual licences used are the Ⓕ MirOS licence, and (for BSD compatibility on other operating systems) the 3-clause UCB licence and the ISC licence; [full terms](TaC-mksh.txt) are available. pdksh originally was public domain, with a few exceptions, but these files are not part of mksh R21 or up. The [mksh(1)](htman/i386/man1/mksh.htm) author (mirabilos) acknowledges the contributions of these people who dedicated pdksh and oksh to the public, and asserts a collective copyright on the code. All these licences are DFSG clean and conform to the OSD, and the MirOS Licence is listed on the pages of the ifrOSS licence centre as well as in the FSF/UNESCO Directory of Free Software. The MirBSD Korn Shell is [OSI Certified](permalinks/news_e20081114-nn.htm)  and its [manual](/man/mksh.1) is [Open Knowledge](http://www.opendefinition.org/1.0).

 To compile mksh, you will need a Bourne or POSIX shell (Solaris /bin/sh is enough, the Z shell works), a C compiler, system and C library header files and the standard C runtime. You will also need a set of standard UNIX® tools on a supported operating system: any recent BSD; Darwin, Apple Mac OSX; Interix (Microsoft® Services for Unix 3.5, maybe Subsystem for Unix Applications on Win2003/Vista); GNU/Cygwin; UWIN; GNU/Linux (libc5, glibc, dietlibc, µClibc, some klibc systems are tested), Debian GNU/kFreeBSD, GNU/Hurd or GNU/Linux; Sun Solaris (8, 9, 10, 11), OpenSolaris; AIX; IRIX; HP-UX 11i; OSF/1; ULTRIX; Minix 3; NeXTstep (but not OpenStep 4.2); QNX; BeOS (with limitations) or Haiku; Xenix, SCO OpenServer 3.2r4.2 or 5 (with limitations) or 6 or SCO UnixWare; Minoca OS; …  
 To run the regression test suite, you will need a not too antiquated Perl optimally with POSIX.pm or Errno.pm as well as [/bin](mksh_old.htm#editor)/ed (whose installation is strongly suggested anyway, because it’s the standard FCEDIT history editor and standard UNIX® text editor), as well as a controlling terminal, usually /dev/tty or provided from [script(1)](htman/i386/man1/script.htm) or GNU screen.

 To use mksh, you only need the C runtime (and any supplemental libraries the binary was linked against) and, optionally, /bin/ed — for interactive use, a controlling terminal is highly recommended because job control does not work without one.

 To make full use of [mksh(1)](htman/i386/man1/mksh.htm)’s interactive features, it is recommended to copy the dot.mkshrc file from the source distribution as ~/.mkshrc into the user’s home directory and let the user adjust it to suit his needs. The sample file configures a few aliases and shell functions as well as a sensible prompt ($PS1) and some csh-like directory stack functions and zsh-like hooks. Full use of this file requires a few special UNIX® tools. Note that $ENV must not be set for [mksh(1)](htman/i386/man1/mksh.htm) to parse the ~/.mkshrc file at startup.

 Support
 -------

 We provide an online manual page in [HTML](/man/mksh.1) and [PDF](/MirOS/dist/mir/mksh/mksh.pdf) format. Reading books about Korn Shells in general is recommended as further help, but beware of the [differences](mksh_old.htm#contrib) (ATTENTION outdated content behind that link) to other shells. Some ISBNs are listed at the end of the manual page.

 A collection of some frequently asked questions is available as the [mksh FAQ](mksh-faq.htm).

 If you require additional assistance or want to discuss bugs, features or enhancements, write to the [miros-mksh mailing list](rss.htm#lists) (or subscribe to it by sending an eMail to the [postmaster](mailto:postmaster@mirbsd.org) telling which address to subscribe to which list(s) — in your case, the miros-mksh list, but we have [more mailing lists](rss.htm#lists)). The mailing list can be reached via the GMane archive using either [NNTP](nntp://news.gmane.org/gmane.os.miros.mksh) or [HTTP](http://news.gmane.org/gmane.os.miros.mksh), or at [The Mail Archive](http://www.mail-archive.com/miros-mksh@mirbsd.org/), although not at MARC. Joining the [IRC](irc.htm) channel #!/bin/mksh (no joke, this is really the channel’s name) is recommended as well.

 Installation
 ------------

 Skip to the section about being [included in operating environments](#otheros) unless you really want to compile mksh from source yourself or create a package for your operating system of choice.

 First off, you have to download the source code from any of the mirrors listed below, or any other mirror you know of. Alternatively, use the [development version](#getcvs) from CVS. Official source code distributions are digitally signed with [gzsig(1)](htman/i386/man1/gzsig.htm) using the MirOS Project’s [current signature key](/gzsigkey.cer). Please verify the signature _as well as_ the hashes and/or checksums below, so you’re sure the content is intact and the version number on the archive is correct.

### Known Mirrors

*   [http://www.mirbsd.org/MirOS/dist/mir/mksh/mksh-R59c.tgz](http://www.mirbsd.org/MirOS/dist/mir/mksh/mksh-R59c.tgz)
*   [http://pub.allbsd.org/MirOS/dist/mir/mksh/mksh-R59c.tgz](http://pub.allbsd.org/MirOS/dist/mir/mksh/mksh-R59c.tgz)

### Checksums and Hashes

*   SHA256 (mksh-R59c.tgz) = 77ae1665a337f1c48c61d6b961db3e52119b38e58884d1c89684af31f87bc506
*   RMD160 (mksh-R59c.tgz) = fd4160e431aaf471aa56029b557b0c446f3aa33b
*   TIGER (mksh-R59c.tgz) = 19aa20121ba0b619f8be7c7bf3466898c8456d989a6fe318
*   1608340960 442736 /MirOS/dist/mir/mksh/mksh-R59c.tgz
*   MD5 (mksh-R59c.tgz) = 99f8ac3c1d8a30b913d509f1969a4aaa
*   All official distfiles are [gzsig(1)](htman/i386/man1/gzsig.htm)d. with our [current signature key](/gzsigkey.cer).

### Preformatted Documentation

*   [catman](/MirOS/cats/mir/mksh/mksh-R59c.cat1.gz) — [lksh](/MirOS/cats/mir/mksh/lksh-R59c.cat1.gz)
*   [XHTML](/MirOS/cats/mir/mksh/mksh-R59c.htm.gz) — [lksh](/MirOS/cats/mir/mksh/lksh-R59c.htm.gz)
*   [PDF](/MirOS/cats/mir/mksh/mksh-R59c.pdf) — [lksh](/MirOS/cats/mir/mksh/lksh-R59c.pdf)
*   [plaintext](/MirOS/cats/mir/mksh/mksh-R59c.txt.gz) — [lksh](/MirOS/cats/mir/mksh/lksh-R59c.txt.gz)

### Decompression

We’re using [gzip(1)](htman/i386/man1/gzip.htm)\-compressed POSIX us[tar(1)](htman/i386/man1/tar.htm) distfiles nowadays, so a simple tar -xzf mksh-R59c.tgz will work. It will create all files in a subdirectory ./mksh/.

### Patching

If you’re a packager/vendor and need to patch mksh and deviate from the default behaviour for that version which is indicated from $KSH\_VERSION, define the [cpp(GNU)](htman/i386/manINFO/cpp.html) KSH\_VERSIONNAME\_VENDOR\_EXT macro to a C string beginning with a space and a plus sign, followed by a tag of yours, e.g. add \-DKSH\_VERSIONNAME\_VENDOR\_EXT=\\"\\ +aCoolDistro\\" to CPPFLAGS so they can be distinguished. I think this is a reasonable request.

In contrast to the old patching mode, this does not require patching the testsuite any more.

### Compilation

In the currently recommended mode of installation, the source code is compiled twice, once for mksh and once for lksh, in different build directories. It’s possible, even customary, to build them with diverging options — e.g. it’s strongly recommended to build lksh with \-DMKSH\_BINSHPOSIX so it auto-enables set -o posix when called as /bin/sh; linking it statically is also very common, although less wise when using glibc; some add \-DMKSH\_BINSHREDUCED and/or the [printf(1)](htman/i386/man1/printf.htm) builtin as well.

##### Building mksh

Consider reading [operating environment-specific notes](mksh_oe.htm) first. **RUN THE TESTSUITE after building** (or, when cross-building, on the target system); several “alternative libcs” and other environments have _known_ bugs that _cannot_ be detected at configure or compile time (otherwise, we’d do that already).

Now you’re in the source code directory; Build.sh does all the magic for you. In theory, invoking the command  
% /bin/sh ./Build.sh  
should work. Relative paths can be used too, for example, instead of [cd(1)](htman/i386/man1/cd.htm)ing to the source directory, you could’ve done  
% mkdir build; cd build; /bin/sh ../mksh/Build.sh  
Doing such an “out-of-tree” build is recommended.

It is optionally possible to place files, such as printf.c, into either the current or the source directory. It will need a compile option (see below) to be activated. printf.c is undesirable because it uses stdio, floating point and bloats.

The build script requires a Bourne shell (Solaris /bin/sh, the [Heirloom sh](http://heirloom.sourceforge.net/sh.html), DEC OSF/1 V2.0 /bin/sh), Korn shell (ksh, ksh88, ksh93, pdksh, mksh, oksh, maybe the MKS ksh), POSIX shell (posh, /usr/xpg4/bin/sh, ash, dash, yash), a related shell (J�rg/Jvrg/Joerg/Jörg Schilling’s bosh or sh, or the Z Shell), or a Bourne or POSIX superset (such as GNU bash) to work; the ULTRIX /bin/sh or the C shell (csh, tcsh) or “bsh” or a scripting shell like the wish won’t.  
Accepted arguments are:

*   \-A — instead of adding the autoconfiguration results to $CPPFLAGS, write them into a file; for when command line or compiler limits would otherwise be reached
*   \-c _mode_ — set compiler mode:
    *   dragonegg to use the LLVM Dragonegg plugin with GCC
        *   llvm to compile to bytecode, optimise there (see the \-O/\-o options) and link with LLVM tools
            *   The options combine and lto were removed, as link-time optimisation has proven to be too fragile in compilers.
            *   \-g — build with debug info, Valgrind and LLVM/Clang scan-build assertions, and \-DDEBUG in place
            *   \-j — parallel build
            *   \-M — do not compile but create Makefrag.inc
            *   \-O — (default) with “-c llvm” use “-std-compile-opts”
            *   \-o _opts_ — with “-c llvm” use these optimisations
            *   \-Q — be (only) a little less verbose
            *   \-r — don’t try to build a pre-formatted version of the manual page using [nroff(1)](htman/i386/man1/nroff.htm) if found — _recommended_
            *   \-v — display version and exit

            Note: “-M” is incompatible with “-c _somemode_” and “-j” — specify LTO and parallel make using your [make(1)](htman/i386/man1/make.htm) tool’s facilities instead. Also, “-c dragonegg” does not work with “-j” (the former is ignored).

            Note: any kind of “-c _somemode_” optimisation is brittle: LLVM (both llvm and dragonegg) have not been used for a long time; GCC’s LTO breaks so often we forcibly disable it nowadays and stopped offering it. **Run the testsuite** if you use one!

            The [build script](cvs.cgi/src/bin/mksh/Build.sh?rev=HEAD) also honours some environment variables detailed at its end.

            Install this binary as /bin/mksh and its manual page; you may want to also install dot.mkshrc, either directly into the skeleton directory, or with [a wrapper /etc/skel/.mkshrc file](http://anonscm.debian.org/cgit/collab-maint/mksh.git/plain/debian/.mkshrc) that reads /etc/mkshrc, especially if packaging for a GNU distribution.

##### Building lksh

Add the \-L flag to the Build.sh to create [lksh(1)](htman/i386/man1/lksh.htm), a variant of the shell that uses POSIX-compliant arithmetics with the host “long” data type, instead of mksh’s guaranteed-reliable 32-bit arithmetics. You probably want to add \-DMKSH\_BINSHPOSIX and, possibly, \-DMKSH\_BINSHREDUCED to the command line and install the lksh binary as your system /bin/sh if you go that route. (This shell is not intended to be used interactively. Its purpose is to run legacy sh scripts (especially with the MKSH\_BINSHREDUCED option) and POSIX sh scripts, including Debian maintainer scripts.)

Install this binary as /bin/lksh and its companion manpage, but remember that it does not come stand-alone and to always ship the full proper mksh shell alongside it.

#### Operating Environment-specific notes

… are now on [their own page](mksh_oe.htm).

### After compiling

The Build.sh script generates an executable (“mksh”, except on GNU/Cygwin, where it is called “mksh.exe”), a shell script to use the newly built mksh to run the regression test suite (“test.sh”), and (unless the \-r option was given) a pre-formatted manual page (“mksh.cat1”). It also lists installation instructions unless \-Q was provided. Now it’s the time to run  
% ./test.sh -v -f  
in order to see if the shell works. The regression testsuite will exit with errorlevel 1 if any tests failed that are not marked as allowed to fail (e.g. OS dependent) or expected to fail, 0 otherwise. Omit the ‘-f’ option if you do not have a fast (say 1½ GHz Pentium-M) machine.

The regression tests need a controlling tty. Please ensure you have one, even for bulk/dæmonised builds; you can use GNU screen or [script(1)](htman/i386/man1/script.htm) to provide one by running the testsuite inside it (see the Debian and OpenSuSE Buildservive packaging for examples of how to do it). If, however, you absolutely cannot get the necessary utilities and devices installed in the build chroot, run: ./test.sh -v -C regress:no-ctty

To actually install mksh, copy the binary to some place in $PATH, i.e. /bin/mksh, $HOME/.bin/mksh, /usr/local/bin/mksh, or whatever your packaging system wants; strip it and run chmod 555 on it. (This can easily be achieved with [install(1)](htman/i386/man1/install.htm) — on Solaris, this is /usr/ucb/install not /usr/bin/install – with the arguments -c, -s, -m 755¹, and -o/-g. ① with 555, [strip(1)](htman/i386/man1/strip.htm) cannot write the file any more, chmod 555 afterwards.) Also append its installation path to /etc/shells, install the dot.mkshrc file (usually alongside with the copyright file and other documentation), copy it to /etc/skel/.mkshrc if your operating environment has this means to include default dotfiles; install either the catman page (mksh.cat1) to, for example, /usr/share/man/cat1/mksh.0, or the mdoc page (mksh.1) to the standard location (/usr/share/man/man1/ or /usr/man/man1/ or whatever your operating environment requires). The manual page requires the Berkeley mdoc macros (either the BSD or the GNU groff version) to be installed during formatting time.

Note that a ~/.mkshrc file will _not_ be executed if $ENV is set and not empty, nor is there an /etc/mkshrc.

For packagers: Upgrades
-----------------------

**Note:** This is _not_ [the ChangeLog](#clog), these are the packager-visible upgrade notes regarding changes in the build system (Build.sh and friends, compiler support, packaging conventions, bad examples, etc). This is also _not_ [the users' upgrade caveat list](#caveat).  
Packagers also please note: it’s mksh or “The MirBSD Korn Shell” (“MidnightBSD Korn Shell” is also appropriate), but _never_ Mksh or somesuch!

_current_: Please remember to subscribe to the mksh mailing list, either directly or via GMane, if you have an interest in mksh, such as packaging it. Thanks!  
[Building lksh](#compile_lksh), _with_ \-DMKSH\_BINSHPOSIX, and installing it alongside mksh, is now recommended more strongly, as only lksh -o posix is close to POSIX compliant. The cat and sleep builtins are gone, so linking either as multi-call binary will now fail; a [portable MirBSD sleep](subprj.htm#sleep) is available to plug the hole if your system utility lacks sub-second sleep support. Please update all cached references to our IRC channels, the network we had been using was obliterated. printf.c updated. The testsuite’s default UTF-8 locale is now C.UTF-8 (except on HP/UX where we know better) so use \-U if you don’t have that. When passing \-DMKSH\_ASSUME\_UTF8={0|1} in CPPFLAGS now also set HAVE\_SETLOCALE\_CTYPE=0 in the environment as the former used to imply the latter but is now going to go away with locale tracking. GNU’s [sigabbrev\_np(3)](htman/i386/man3/sigabbrev_np.htm), [sigdescr\_np(3)](htman/i386/man3/sigdescr_np.htm) and [strerrordesc\_np(3)](htman/i386/man3/strerrordesc_np.htm) are now preferred over \_sys\_signame\[\], \_sys\_siglist\[\] and \_sys\_errlist\[\]/sys\_nerr respectively if present. **Read [musl-specific notes](mksh_oe.htm#oe_musl) if building for musl! RUN THE TESTSUITE!** _(unfinished…)_

R59c: Please remember to build and install the HTML FAQ. Ignore deprecation warnings regarding sys\_errlist and sys\_nerr as alternatives will be used automatically once these are not available any more (glibc users). When using GNU coreutils consider patching dot.mkshrc to drop the \-o option from lo.

R59b: Correction: Normally, that link goes from rksh, or just ship both.

R59: You can install a link from rmksh to mksh (same for lksh or sh). If necessary, an R58b with the fixes but not the breaking changes can be spun; contact me if needed.

R58: _in-tree build of FAQ is broken_, sorry — build out-of-tree or [with this hotfix](http://www.mirbsd.org/cvs.cgi/src/bin/mksh/Build.sh.diff?r1=1.752;r2=1.753) instead (cause was Build.sh removed mksh.faq…). GCC’s LTO support was, as announced, removed. Do _not_ build with LTO if you have GCC as compiler, it has wrong-code generation bugs! We try to add \-fno-lto to CFLAGS if GCC is detected, since some GNU distributions forcefully enabled LTO by default despite the bugs and upstream not caring about them. The FAQ is now shipped as XHTML snippets with the source code; run FAQ2HTML.sh to build a valid local HTML page, consider installing it

R57: The MKSH\_EARLY\_LOCALE\_TRACKING code was fixed. The testsuite now checks whether there is actually a controlling tty available or not and whether it matches what’s passed for options. The [vendor patching](#vendorpatching) info was updated.

R56c: SuSE provided a patch to implement mediæval-scope locale tracking (set ±U if the POSIX locale variables change within the shell); this is provided as-is, use with care, and especially do _not_ use it in a system shell (with \-o posix, it throws a warning when triggered, as it invokes non-compliance).

R56b: The offsetof macro of dietlibc and klibc, which is upstream-buggy, is overridden with GCC 3+ to avoid a warning.

R56: Building with -DMKSH\_ASSUME\_UTF8=0 no longer causes a known failure in the testsuite. Building with dietlibc or klibc though causes a warning about offsetof and dynamic “command”. You can now choose which UTF-8 locale to use with test.sh -U.

R55: make repool needs mksh R55’s bugfix on the host. OS/2 builds with “textmode” (CR+LF as newline) now need Build.sh -T. Persistent history is now supported by lksh as well, unless explicitly disabled. There were some changes related to the build system.

R54: Build.sh now installs both manpages (lksh.1 and mksh.1) independent of how it’s called. Several additional compiler flags are attempted. Porters to Harvey-OS and OS/2 should review their patches.

R53a: this is a botched R53.

R52c: prepare to review use of set +o.

R52b: nothing of note, but prepare to review all mksh scripts to ensure they start with export LC\_ALL=C soon.

R52: Android can define MKSH\_DEFAULT\_PROFILEDIR itself but we don’t. We no longer ship the stop alias.

R51: Please review all mksh scripts, such as a skeleton ~/.mkshrc file, for alias safety and security — in case of doubt, contact us. The EBCDIC and OS/2 ports are not finished, but some improvements are already included. CVS snapshots now use ‘j’ ipv ‘i’ making room for one more stable version; after R51, we will release R53, mostly bugfixes, and roll them all up in R50g.

R50f: If you patch mksh, please do not only update the version in check.t (twice) and sh.h but now in mksh.1 as well; thanks!  
Please let the mksh developer team review your .mkshrc files for robustness!

R50e: Better portability; no conflict with system headers defining a “tilde” function; no use of ptrdiff\_t any more. The old workarounds for static code checkers are gone. NSIG generation works with GCC 5.

R50d: Nothing to note.

R50c: New HAVE\_ISSETUGID define. The example Debian /etc/skel/.mkshrc moved. **Security release.** [Details.](permalinks/wlog-10_e20141003-tg.htm)

R50b: test.sh output is now clearer.

R50: test.sh now uses $TMPDIR. If you want to build without SSP, define HAVE\_CAN\_FSTACKPROTECTORSTRONG in addition to HAVE\_CAN\_FSTACKPROTECTORALL if you have GCC 4.9+.

R49: There is now generated content at build time; it is known that this is beyond the capabilities of some shells such as Coherent /bin/sh. We plan to address this in a later release by rewriting the relevant parts in C, so that a _host_ C compiler will, in addition to a _target_ C compiler, also be required to build mksh.

R48b: Nothing of notewortiness.

R48: We now ship a Windows® icon; just ignore it if you don’t want it. We regularily update dot.mkshrc so you’d better think of a way for your users to get those updates.

[older entries](mksh_old.htm#upgrade)

Download the development version via CVS
----------------------------------------

You can use [cvs(GNU)](htman/i386/manINFO/cvs.html) to download the development version of [mksh(1)](htman/i386/man1/mksh.htm), commonly called HEAD (or “trunk” to some). Beware of bugs though we strive to make it installable (at least on MirBSD ☺) at all times.

% env CVS\_RSH=ssh cvs -qd \_anoncvs@anoncvs.mirbsd.org:/cvs co -PA mksh

You might also want to get the printf.c builtin, but this is optional, strongly discouraged and use it only if you really must:

% env CVS\_RSH=ssh cvs -qd \_anoncvs@anoncvs.mirbsd.org:/cvs co src/usr.bin/printf

Installation instructions as [above](#compile), although the Build.sh options, CPPFLAGS, etc. might have changed a little in the meantime. In general, you want the following:

% cd mksh
% sh Build.sh -r

Optionally set CC and other variables, as usual.

### Unofficial git mirror

[github](https://github.com/MirBSD/mksh) (chosen only for popularity) hosts a read-only, push-only, possibly nōn-fastforward, unofficial git mirror of the mksh source tree. Use at your own risk.

Users' Upgrade Caveat
---------------------

This does not necessarily list new features, only these which users should be aware of for existing scripts.

_current_: The cat and sleep builtins have been removed. In restricted shells, HISTFILE is now read-only. _Do not_ rely on the BOM enabling UTF-8 mode or turning on POSIX mode disabling UTF-8 mode any more, full locale tracking may drop these, and only the LANG and LC\__\*_ variables (and manually running set ±U and that being restored upon returning from Korn-style functions) determine UTF-8 mode then. (A preview of this change is already available via Debian bullseye, but more remains to be done.) The Emacs mode editing command capitalize-word\[sic!\] was renamed to capitalise-word (to fix spelling), prev-hist-word to prev-hist-bigword (consistency with the new bigword commands). Converting variables imported from the environment to integer will discard their value if it isn’t purely numeric, for security reasons (“taint”). The IRC channels moved to a different network. Escaping was improved and thus, for some characters/bytes, changed. Builtins now error out if they returned true otherwise but encountered write errors on stdout. Expect persistent history to require PostgreSQL in the future for reliability. If an environment variable occurs more than once on shell startup, the last match used to win; this is changed to the first for consistency with libc even if this mismatches other duplicate resolution algorithms. The kill-region editing command used to be bound to ^W like in Emacs, but ^W is usually taken by WERASE so it was moved to Esc+^W so users reading the manual page aren’t confused about what it does. The caret notation used by bind changed, see its documentation in the manpage, or the 2021-09-26 IRC heads-up mesaage, for details. Mapping of raw octets in UTF-8 mode was moved from U+EF80‥U+EFFF to U-10000080‥U-100000FF (out of the PUA and past anything actually occupied by UCS) except postponed until the shell version will identify as R60. Value substitutions now handle exit (also set -e, etc.) correctly; function substitutions still don’t for AT&T ksh93 compatibility. BOM (byte order mark) handling removed. A subtle change to the hash algorithm (affects both ${var@#} and the Lbafh\_\* functions in dot.mkshrc) delivers better performance but no overall degradation in avalanche / quality; the hashes of anything not a single byte change from older releases’, though. lksh LONG\_MIN/-1 now properly raises an implementation-defined signal (SIGFPE on MirBSD) if the result is \> LONG\_MAX. Escape a caret if it is the first character in a shellglob group \[\\^a-z\] since the unescaped meaning may be changing to \[!a-z\] at some point. _(unfinished…)_

R59c: On Mac OSX 10.4 and up, ulimit -m is now an alias for ulimit -v, which was the one older versions had (so pkgsrc® can use it consistently). Some changes to path normalisation and here document handling might introduce breakage, but we hope they only _correct_ things ☻ Also, read the FAQ.

R59b: The output format of set +o changed.

R59: On OS/2 the test/\[/\[\[ builtins now add executable file extensions to several more checks. The output of some commands changed adding quoting for re-entry safety. Restricted mode is now enabled if the shell is called as rmksh, rsh, rlksh, …. The right-hand side of a string comparison (=, ==, !=) in \[\[…\]\] now uses full Korn Shell extglobs (breaking, but eliminating the need for many eval). There’s now a which function in dot.mkshrc. The global builtin is gone (use typeset -g from R55+ instead), breaking.

R58: HISTSIZE is now limited to 65535, as pre-announced for years. Running set -p interactively in privileged shells obtains the effective privileges.

R57: Bugfix / rollup release, with only a few changes — it has some known bugs; no (known) regressions though.

R56c: Bugfix-only release; some fixes might cause new warnings

R56b: Bugfix-only release

R56: Aliases support ‘.’, ‘:’ and ‘\[’ in names again (though “\[\[” is still forbidden). POSIX character classes and the BSD [re\_format(7)](htman/i386/man7/re_format.htm) extensions \[\[:\\<:\]\] and \[\[:\\>:\]\] (quoted due to shell syntax issues) have been added (ASCII/EBCDIC only). Some experimental changes to the history code might help with the vanishing entries phenomena. Switching to POSIX mode now disables UTF-8 mode and forces exec to a PATH search and to use [execve(2)](htman/i386/man2/execve.htm). In dot.mkshrc the hd\_mksh function to hexdump using builtins is now always available, and **the default editor selection has changed**: it’s moved to near the top of the file and now has a priority list users can change.

R55: The POSIX declaration utility concept is introduced, which also applies to commands having variable assignments and redirections preceding them. wait however does not keep assignments any longer. The new \\builtin utility forwards the declaration utility flag exactly like command does. The new typeset -g replaces mksh’s previous home-grown global builtin, which is now deprecated and _will_ be removed from a future version. Aliases are now expanded for command, function and value substitutions at parse time (like for functions, and excepting accent gravis-style substitutions), and typeset -f output is alias-resistent; furthermore, alias names are now limited to \[A-Za-z0-9\_!%,@\], following POSIX, although a non-leading hyphen-minus is also permitted. print -R is now (correctly) roughly equivalent to the POSIX mode echo. The deltas between mksh and lksh, and between normal, POSIX and “SH” mode, are now properly documented in the manual pages. The let\] hack is gone. ulimit -a output changed to display the associated flag. $PATHSEP is now pre-defined to ‘:’ (‘;’ on OS/2). $LINENO is now incremented better in eval and alias expansions.

R54: Lazy evaluation side effects and set -e\-related error propagation in || and && constructs are now handled properly.

R53a: Tilde expansions of parameters (~, ~+, and ~-) now strip . and .. components from their results. The sample PS1 in dot.mkshrc was corrected for users whose home directories are præficēs of others’. Rotation operators were renamed from <<< and \>>> to ^< and ^>. var=<< may now be used. Many fixes.

R52c: Prepare to audit all uses of set +o. Handling of "\`\\"\`" is now considered not a POSIX violation, until this issue is officially resolved. Our PDF manpages now use the PA4 paper size enabling printing without the need to scale of crop on both DIN ISO A4 and USA “letter” paper. The manpages now compile with an older version of the mdoc macropackage (in use by e.g. Schillix) installed. command -pv and command -pV now behave POSIX conformant.

R52b: Prepare to audit all scripts to ensure they begin with export LC\_ALL=C as we’ll implement locale trackiing some day. Handling of "\`\\"\`" is now again not POSIX-compliant even in posix mode to unbreak existing code (Austin#1015, mktexlsr). set -C; :>foo is now race-free. Some bugfixes.

R52: (( … )) is now a compound command, which changes the way I/O redirections work. ${x#~}, ${x/y/z}, etc. now have tilde expansion enabled. ${x//#y} no longer works, for anchored patterns use only one slash; quotes are now honoured better in such expressions, though. alias stop='\\kill -STOP' is no longer defined by default anywhere; source is no longer an alias but a built-in utility, unbreaking it in some cases; the lksh hack to remove an alias upon function definition is removed. [issetugid(2)](htman/i386/man2/issetugid.htm) is no longer used for set ±p checks, unbreaking suid in some cases. Handling of "\`\\"\`" is now POSIX-compliant (this breaks scripts)! More bugfixes, although there are (sorry!) still some known bugs ☹

R51: Integers with bases outside of the permitted range are handled as base 10 instead of failing to parse, like ksh93. Korn shell style functions (function foo {) now have locally scoped shell options (e.g. set -o noglob) except in lksh. Much standard code is now protected from being overridden by aliases; the new enable function in dot.mkshrc can be used to enable or disable a built-in utility (such as rename) or function (including those in dot.mkshrc) by means of an alias. The feature to unalias an identifier when a POSIX-style function with the same name is defined only persists in lksh, as it is a legacy feature. [cat(1)](htman/i386/man1/cat.htm), when a flag is given, and [printf(1)](htman/i386/man1/printf.htm), now prefer an external utility over the builtin reliably. Several bugfixes, such as command -v now handling shell reserved words, impact compatibility.

R50f: unset HISTFILE actually works. Several more bugfixes and robustness improvements. The [mksh(1)](htman/i386/man1/mksh.htm) manpage now documents how to enable/disable the UTF-8 mode based on the current POSIX locale according to how it’s done at startup on some OSes.

R50e: **Warning:** do not use x=<< inside a function, it has never worked.  
Lots of POSIX compliance and bug fixes. New options for the exec builtin.

R50d: Fixed a segfault and a regression in field splitting breaking update-initramfs. Sorry! Also, added a warning about not using unchecked user input in arithmetics — \[\[ $x = +(\[0-9\]) \]\] || die is a useful check. We’ll link a more detailed writeup about it later.

R50c: $RANDOM is no longer exported. Field splitting has improved. This version fixes one security issue of low importance ([details](permalinks/wlog-10_e20141003-tg.htm)) which is mksh-specific, and mksh is not vulnerable to all those GNU bash bugs, some of which affect AT&T ksh93 as well.

R50b: nameref can alias $1, etc. again.

R50: Arithmetic expressions are now IFS-split, as per POSIX; this matches what the manpage always documented. Due to regressions, the arr=(\[index\]=value) syntax (naming the indicēs during setting an array) is gone for now, and will not reappear in “set -A”, only in the “=(…)” syntax once we get its parsing fixed. Privileges are now dropped upon start unless the shell is started with “-p”.

R49: The hash algorithm has changed (for, hopefully, the last time); the old algorithms are gone from dot.mkshrc too, and the ${foo@#} syntax no longer accepts a seed value (for more variety use the functions from dot.mkshrc; for hash tables, just xor and rotate the finished stable hash). Some terminal and other issues have been fixed, don’t be surprised.

R48b: Bugfix for multi-line prompts.

R48: The “doch” alias in dot.mkshrc now keeps standard input usable at the cost of the command to be run being logged by [sudo(8)](htman/i386/man8/sudo.htm). If you notice anything unusual (regression) in the interactive display code please report it; sections of that code have been refactored and improved.

[older entries](mksh_old.htm#caveat)

Recent Changes
--------------

Changes in the current (unreleased) development version:

*  Draw all prompt lines on clear-screen (spotted by akko)
*  Fix Lstripcom errorlevel, so it can be used with set -e
*  Fix TOCTOU when calling [readlink(2)](htman/i386/man2/readlink.htm)
*  Let regression-37 actually test what it was supposed to
*  Fix a misrendering in the manpage and use The Queen’s English
*  When restoring shell flags upon return from FKSH functions, never restore ±p (±o privileged) and fix restoring ±m (±o monitor)
*  More const-cleanliness
*  dot.mkshrc: no longer use the built-in [cat(1)](htman/i386/man1/cat.htm)
*  dot.mkshrc: Lstripcom: don’t trash backslashes
*  dot.mkshrc: allow ^D on interactive use of utilities
*  dot.mkshrc: more “set -ueo pipefail” safety
*  dot.mkshrc: fix some more minor issues spotted reviewing
*  check.t: fix some test documentation, cross-reference POSIX more, fix if necessary, make some able to be run with other shells
*  Add RLIMIT\_RTTIME as ulimit -R matching GNU bash
*  Remove [cat(1)](htman/i386/man1/cat.htm) and [sleep(1)](htman/i386/man1/sleep.htm) builtins; point users to the new [portable MirBSD sleep download page](subprj.htm#sleep) — getting signal handling right for them as builtins would be hard and expensive
*  Darwin has st\_mtimespec but not st\_mtim in struct stat
*  Improve installation instructions printed for out-of-tree builds
*   \[chet, tg\] Make HISTFILE read-only in restricted shells
*  Defend against getcwd() syscall on Linux violating POSIX
*  Fix GNU/Hurd codepath path length type, realpath errno
*   \[komh\] Fix jobless build (missing ifdef)
*  Fix struct stat mtime member detection
*  Make "C" the implementation-specified default locale for early-locale-tracking (note full locale tracking will have to use whatever the underlying OS’ is, if no [setlocale(3)](htman/i386/man3/setlocale.htm) it’ll be just "C" again) and document possibly removing turning on POSIX mode disabling and presence of a BOM enabling UTF-8 mode with full locale tracking
*  Document OPTU-16 (U+EF80‥U+EFFF) mapping for raw octets will not be present once mksh will have switched to full 21-bit UCS / UTF-8
*  Add several bigword-based editing commands to Emacs mode
*  Improve documentation wrt. $ENV in the FAQ
*  Document MKSH\_ASSUME\_UTF8 will need to go away with full locale tracking; (see Debian) locale will be federführend even in scripts…
*  Correct several minor/cosmetic issues
*  Add generator code for character classes, more consistent
*  Harden conversion of imported variables to integer, like Perl “taint”: imported variables will now lose the value when converting to integer but they are not purely numeric (CVE-2019-14868 was a similar issue in AT&T ksh); honour \-o posix for leading-zero as octal, though (but continue not in importing array indicēs)
*  Fix lexer token state corruption when reading new input; makes evaluate-region editing command actually useful
*  Use small stack buffers over allocating to reduce malloc pressure in several more codepaths
*  Fix proper escaping/quoting and tab completion for tilde, curly braces and \\x02, either escaped or not
*  Add character class documentation to the manpage
*  Force use of setjmp, which implements [\_setjmp(3)](htman/i386/man3/_setjmp.htm), on Linux-klibc instead of sigsetjmp, which they deliberately broke by ignoring the second (save/restore signal mask flag) argument
*  Small optimisations (less duplication; optimise for the common codepath instead of the uncommon one) in code and testsuite
*  EBCDIC: codepage consistency check, diagnostic; document more
*  Plug a couple memory leaks; slightly increase performance
*  Add new option \-o asis to avoid escaping what are C1 control characters in ISO 8859 and similar codepages; add to FAQ
*  Change ${foo@Q}/typeset -p escaping to honour the current UTF-8 mode flag and escape C1 control characters by default; cease escaping more than necessary (for the mode); cease emitting \\uNNNN escapes in nōn-UTF8 mode
*  Remove references to obliterated IRC network we had been using; point to more generic places, which, once a final new home is found, can be more easily updated
*  Massive code and comment improvements during work on fixing the way special characters (control characters, invalid UTF-8, etc.) are handled or escaped, including emacs mode cursor positioning and output
*  Fixes for possible bugs: side effects in macro call; hi-bit7 VEOF; truncating dynamic string streams in the middle or incorrectly; missing stderr flush on direct builtin call
*  Reduce memory allocator pressure by using more on-stack buffers
*  Avoid splitting multibyte characters during string truncation in some cases, including escape sequences for them
*  Improve outputting job information
*  Harmonise some error reporting and use string pooling more
*  Wrap all builtin calls into a check, run if the builtin would exit true (zero) otherwise, for stdout write errors; diagnostic and exit false if so; addresses Debian #990265 and corresponding thread on Austin Group ML; add corresponding diagnostic also to echo/print builtin
*  Make rotating by 0 avoid C UB… \*sigh\*
*  Add new Build.sh option \-A
*   \[RT, tg\] Port to SCO OpenServer 3.2r4.2 and Xenix (crossbuilt for now)
*  Fix FAQ2HTML.sh on præ-POSIX [sh(1)](htman/i386/man1/sh.htm)
*  Make testsuite not fail on rangeless [tr(1)](htman/i386/man1/tr.htm) or symlinkless system
*  Allow for <sys/select.h> substituting <sys/time.h> if both may not be included at the same time (scosysv 3.2r4.2)
*  Elide some configure-time tests on OEs where they are known
*  Not only is [fgrep(1)](htman/i386/man1/fgrep.htm) unportable, but so is [grep(1)](htman/i386/man1/grep.htm) -F…
*  Calculate the most negative number w/o triggering UB (I want Ͻ…)
*  Improve signedness‑ and const\-cleanliness of code
*  Add [strstr(3)](htman/i386/man3/strstr.htm) and [memmove(3)](htman/i386/man3/memmove.htm) if missing
*  Clear a few more tty flags on makeraw; inspired by ksh93
*  Skip the rename builtin if [rename(2)](htman/i386/man2/rename.htm) syscall is missing
*  Add a signal handling abstraction; still require [sigaction(2)](htman/i386/man2/sigaction.htm) in the normal case, whitelist OSes with reliable [signal(3)](htman/i386/man3/signal.htm) bsd\_signal
*  Xenix has reliable signals but broken [termios(4)](htman/i386/man4/termios.htm); cope
*  Speed up configuring: skip a few checks for ancient compilers
*   \[RT, tg\] Update and promote to working the port to Syllable Desktop; improve the situation for LynxOS 3.0 and BeOS 6.2 “Zeta” and, slightly, for BeOS 5.1 “Dano” and 5.0 “Maui”
*  Check whether exec -a newargv0 prog args… works separately so it isn’t caught through sh-mode-1 indirectly only; split that
*  Begin switching to… slightly less insane… integer types
*   \[RT\] Port to SkyOS (fragile), Minoca OS (good)
*  Sanity-check some usual tools before using (build, test)
*  Handle broken-but-extant [getrusage(2)](htman/i386/man2/getrusage.htm)
*  Make [times(3)](htman/i386/man3/times.htm) use work in the absence of CLK\_TCK
*  Actually act on [getrusage(2)](htman/i386/man2/getrusage.htm) and [times(3)](htman/i386/man3/times.htm) errors
*  When tabcompleting, set the mark to the beginning of the inserted substring (the cursor is at or just one space past the end), similar to how other editing commands behave; for xthechar on IRC
*  When importing env vars, first match now wins, like in libc
*  Exporting parameters to the environment now uses a stable order
*  Move kill-region default binding to Esc+^W because ^W is usually taken by WERASE, to unconfuse
*   \[RT, tg\] Work around NeXTstep [cc(1)](htman/i386/man1/cc.htm) more
*  Testsuite: C.UTF-8 is now the default UTF-8 locale on all operating systems except HP/UX where it still defaults to en\_US.utf8 and Darwin (Mac OSX) which uses just UTF-8 for some reason‽
*  Run all tests with LANG=C since musl defaults to C.UTF-8 if all locale parameters are unset (and talk about Debian glibc to do the same exists and I’m considering this for MirBSD maybe as well)
*  Make base-1 integers pass typeset -p reentry-safe
*  Fix manual page misrendering a few Ns macros with GNU groff
*  Uncouple HAVE\_SETLOCALE\_CTYPE=0 from (soon to be gone) \-DMKSH\_ASSUME\_UTF8={0|1}
*   \[RT\] Make it easier to work around a broken $Config{perlpath}
*  Use extended caret notation in bind input and output
*  Move raw octet mapping off U+EF80‥U+EFFF to U-10000080‥U-100000FF
*  Use extended caret notation in the command line editor, etc.
*  Restore transpose ability to work for nōn-UTF8 characters
*  Make input handling more reliable, prepare some for 21-bit UCS
*  Do not attempt to [fcntl(2)](htman/i386/man2/fcntl.htm) on just-closed file descriptors…
*  Warn if setting or clearing the close-on-exec flag fails
*  Fix test for character device in mksh -T
*  Address Coverity Scan checkers’ complaints
*  Make casting around, EBCDIC, DEBUG builds more reliable
*  Protect tab completion with extended caret notation escaping, reported by lanodan on IRC
*  Make Build.sh -g more useful-ish with other compilers and prefer \-Og over \-O2 for optimisation then
*  Revert turning on POSIX mode turns off UTF-8 mode from R56
*  Advance to renaissance locale tracking; revert defining our implementation-defined default locale to C and use the OS’ (XXX just fix up the changelog entry above for the release)
*  Add ${var@^} for unambiguous extended caret notation
*  Temporarily revert to U+EF80‥U+EFFF raw-octet range until R60
*  Ensure the shell exits nōnzero on internal errors everywhere
*  Drop duplicate, reversed, SIGINT/SIGQUIT handler munging on exec which was only right most of the time (Debian #992885, Vincent Lefèvre)
*  Drop [sigaction(2)](htman/i386/man2/sigaction.htm)/[bsd\_signal(3)](htman/i386/man3/bsd_signal.htm) failure warnings with reason
*  Fix exit (and set -e etc.) in valsubs
*  Clean up \_POSIX\_VDISABLE handling
*  Redo fd saving handling; issues spotted by komh (OS/2), ymd
*  Remove BOM handling entirely
*  Improve autodetection of whether SSP/ProPolice is supported
*  Work around broken \_POSIX\_VDISABLE definition in glibc/kFreeBSD
*  "C" is the implementation-defined default locale, unless the new MKSH\_DEFAULT\_UTFLOC macro is defined, for setlocale-less operation
*  Add debug-buffer editing command #ifdef DF (for developing mksh)
*  Fixes for the MIPSpro compiler
*  Clean up the pre-initio() codepaths
*  Advance less-UB-y arithmetics project: shf\_vfprintf et al.
*  Overhaul error reporting functions avoiding some name doubling
*  Fix if FCEDIT when TMPDIR contains whitespace
*  Tighten locale and charset checks
*  Handle gracefully users doing integer EPOCHREALTIME=
*  Fix newer GCC warning on compile-time asserts
*  Support GNU [strerrordesc\_np(3)](htman/i386/man3/strerrordesc_np.htm) replacement for \_sys\_errlist\[\]
*  Better configure-time detection (TenDRA, dietlibc, …)
*  Fix possible [setsid(2)](htman/i386/man2/setsid.htm) failure in chvt code by always forking, with waiting if !, and communicate child process errors back
*  Change some more numbers to unsigned, signed is evil in C
*  Improve flags documentation, also fixes Debian #999706
*  Clear nonblocking flag on entry for FIFOs as well, as POSIX says
*   \[komh, tg\] Fix termio chvt flushing and link to Ilya Zakharevich’s docs why no shell can use [termios(4)](htman/i386/man4/termios.htm) on OS/2
*  Introduce k32 type and arithmetics, used in hash, indicēs, …
*  Add explicit masking for 8-bit to KBY and KBI macros
*  Change remaining users off stdint.h types, except old arith
*  Limit object size to the smaller of (size\_t)PTRDIFF\_MAX and SIZE\_MAX, so byte representation pointer offsets cannot cause UB
*  PRNG improvements: track traps and history input
*  Limit variable name length to INT\_MAX-X\_EXTRA to guarantee export
*  Update portability glue for manpage
*  Document local array howto and behaviour in the FAQ
*  Fix missing backslash in posix-mode FAQ locale example code
*  Change short hash from BAFH0-1 to BAFH1-0 (faster at no loss)
*  Improve UB-safe type property detection and arithmetics; switch more parts of lksh to UB-y (POSIXly “correct” though…) arithmetics
*  Support GNU [sigdescr\_np(3)](htman/i386/man3/sigdescr_np.htm) replacement for \_sys\_siglist\[\] and [sigabbrev\_np(3)](htman/i386/man3/sigabbrev_np.htm) for \_sys\_signame\[\] (avoid glibc regression)
*   \[RT\] Port to SerenityOS (improving)
*  Build.sh work around FreeBSD [make(1)](htman/i386/man1/make.htm) using set -v
*  Warn about \[^…\] shellglobs because some people currently are trying to change POSIX to force GNU bash behaviour there instead of (currently) permitting both traditional/ksh and GNU bash behaviour ☹☹☹  
    (currently) disabled for lksh \-o posix, for sh vs autotools…
    *  Correct set -o allexport description
    *  Work around older dietlibc’s lack of some limit macros
    *  Clear builtin\_argv0 when quitenv()ing E\_EXEC env
    *  Fix selftest-tty-absent and thus FTBFS on Hurd and GNU/kFreeBSD
    *  Correct R41 regression wrt (nōninteractive) tty state restoring
    *  dot.mkshrc also add ~/.local/bin/ to $PATH if extant
    *  rename bool/true/false/tobool() to Wahr/Ja/Nee/isWahr()
    *  drop use of pure attribute, until revisited (and with const)
    *  reduce UB in arithmetics further (and IB…)
    *  FAQ: note line number reporting issue for blocks
    *  improve Makefrag.inc generation (Build.sh -M)
    *   \[Coverity\] improve padding/unused in onstack Getopt structure
    *  fix shift in value substitutions and function substitutions
    *  improve compile-time checks and run more but not redundant ones
    *   TODO: mksh\_ari\_u must go, it’s never correct… \*sigh\*

    R59c bundles tons of bug and portability fixes:

    *  Update character widths (Jamo bugfix)
    *   \[spellintian\] Fixes
    *   \[Jonathan Perkin\] Don’t use “test -e” in Build.sh
    *   \[Jonathan Perkin\] Mac OSX-specific: ensure ulimit -m is present even if it is an alias of ulimit -v (10.4+), for compatibility
    *   \[Finn Thain, Stanley J. Johnson\] Port to A/UX
    *  Add older [ulimit(2)](htman/i386/man2/ulimit.htm) support, if [setrlimit(2)](htman/i386/man2/setrlimit.htm) is missing
    *  More EBCDIC-safeness (slightly…)
    *   \[PerlAcademy\] Allow all tests to pass with very old Perl 5
    *  Fix test.sh’s output of tested/expected shell version
    *   \[Stanley J. Johnson\] Let A/UX default CC to gcc
    *  Drop “is being ported” warning from A/UX and OS/2, they work
    *  Include <pwd.h> only if MKSH\_NOPWNAM is not defined
    *  “command -v” must print absolute pathnames, even if $PATH contains relative pathnames under which the command in question was found (orbea)
    *   \[komh\] Fix absolute pathnames relative to / on nōn-OS/2, too
    *  Fix some more corner cases related to pathname normalisation
    *  FAQ: “${@?}: bad substitution” documentation
    *  Fix some constructs pointed out by https://www.deepcode.ai/
    *  Clean, refactor, optimise some code
    *  Allow ^Xe on empty command line; quote editor argument properly
    *  FAQ: an IRC user suggests ^Xe for ad-hōc scripts and multiline
    *  Eliminate many unnecessary calls to (re‑)allocate memory
    *  Correct order during tree-printing of heredocs (LP#1783355)
    *  Drop some possibly unreached and probably broken code
    *  Increase FAQ2HTML.sh compatibility with pre-POSIX shells
    *  Demote some (unlikely called) output code to !MKSH\_SMALL

    R59b is a must-have bugfix upgrade for R59 (not R58):

    *  Handle other tmux $TERM types, pointed out by multi via IRC
    *  Fix typo in FAQ
    *  y='a\\\*b'; \[\[ $x = $y \]\] regression (Martijn Dekker) fix
    *   \[l0kod\] Defuse CLIP OS O\_MAYEXEC support (cf. LWN)
    *  Make set +o output a command to restore the currently set and (new!) cleared options, keep a reset state per session (experimental)
    *  Correct documentation and code regarding to argv\[0\] parsing: first ‘-’ for login shells, then ‘r’ case-insensitively for restricted shell, then “sh”\*, again case-insensitively, for BINSH\_\* modes; add tests
    *  On OS/2, allow case-insensitive name for direct builtin call
    *  Always skip startup files if direct builtin call
    *  Avoid some sometimes-redundant startup codepaths

    R59 has some major fixes, also introducing breaking changes:

    *  Repair out-of-tree builds (noticed by rsc)
    *  Work around a glibc on Hurd issue in testsuite
    *   \[komh\] OS/2 filesystem mtime granularity is two seconds (as in FAT)
    *  Replace while with goto: Coverity was confused
    *  Fix invocation of some builtins when external utility absent
    *   \[komh\] Improve automatic executable suffix for test builtin
    *  Style code, refactor, clean up, optimise
    *  Use cached egid in test builtin
    *  Make bind builtin output reentry-safe; safety fixes
    *  If basename(argv\[0\]) after leading dash removal begins with an ‘r’ enable restricted shell flag; reported by pmjdebruijn via IRC
    *  Fix code example in manpage for how tab completion escapes
    *  Match full extglob pattern RHS of \[\[ string comparison like ksh93
    *  Implement which with \-a in dot.mkshrc
    *  Remove global builtin (use typeset -g)
    *  alias, command, whence: Print alias names quoted
    *  Implement a new quote-region (Esc+Q) editing command
    *  Document all built-in aliases (requested by msiism via IRC) and those aliases and functions shipped in dot.mkshrc; completely overhaul builtin and reserved word documentation, for consistency
    *  The manual page now features properly spaced em dashes ☻
    *  Document that test x = y doesn’t extglob, only \[\[ x = y \]\] does

    R58 contains a lot of fixes and improvements:

    *   \[lintian\] hyphen-used-as-minus-sign (on jessie, not later, ‽‽‽)
    *  Fix system info gcc dump{machine,version} shell escaping level
    *  Document KSH\_VERSIONNAME\_VENDOR\_EXT in Build.sh
    *  Be more explicit about the LTO bug exposed by check.t
    *   \[Todd C. Miller\] Add -x (file locks) and AIX-specific -r ulimits
    *  Handle Midipix as test environment and fix some warnings
    *  Fix some Build.sh issues as Mirtoconf is now used by [MirCPIO](pax.htm) and [MagicPoint](mgp.htm)
    *   \[komh\] Improve CRLF to LF conversion
    *   \[komh\] Ensure ECHO mode is enabled at startup so read has local echo
    *   \[komh\] Let check.pl retain the PERLIO env variable
    *   \[komh\] Unbreak nounset-1 test on systems with drive letters
    *   \[komh, tg\] Make ulimit-3 test work without |& (that is, incomplete ports, i.e. those with \-DMKSH\_NOPROSPECTOFWORK)
    *  Disable xxx-stat-1 test for now, fails when run as root
    *  Drop Build.sh flags \-c combine, \-c lto
    *   \[Martijn Dekker\] Exit 126 on [execve(2)](htman/i386/man2/execve.htm) failure, not 1 (e.g. E2BIG)
    *  Behave set and export/readonly-on-read-only-variables when run with command and command dot, bugreports by Martijn Dekker
    *  dot.mkshrc: simplify; enhance (un)setting locale example
    *  Catch build errors earlier
    *  Add \-fno-lto (if GCC is detected) to CFLAGS and LDFLAGS
    *  Limit HISTSIZE to 65535, as long pre-announced
    *  Unbreak testsuite selftest-tty-absent for lksh
    *  Begin work on support for neatcc (needs neatcc to evolve first)
    *  Fix possibly not enough aligned access in struct job
    *  Support going full setugid by running “set -p” once interactive
    *  Document another (arcane, almost nowhere needed) definition
    *  Improve code legibility and testsuite reliability and maintenance
    *  Speed up trivial += cases (LP#1855167)
    *  Some further code and memory optimisation and test coverage
    *  Document that += is always string append (LP#1857702)
    *  Fix “set -e appears active within eval but isn’t” reported by Martijn Dekker and another bug related to using set ±e inside eval
    *  Handle parameter assignment in front of invocations of POSIX-style functions like ksh-style ones and external utilities; cf. Debian #935115
    *  Fix bad memory access for invalid syntax (LP#1857828, LP#1857826)
    *   \[Brian Callahan\] Update MALLOC\_OPTIONS-using testcase for newer OpenBSD
    *  Support lacc as compiler (just detecting, no change), thanks Brian
    *  Share \_\_IDSTRING with [jupp](jupp.htm)
    *  Update string comparison/pattern documentation
    *  Document vi command line editing mode state better
    *  Add FAQ2HTML.sh to convert mksh.faq to local valid XHTML+CSS
    *  Correct backslash expansion documentation; caveat re. 16-bit UCS
    *  Fix extra empty field on IFS-NWS trim expansion (Martijn Dekker)
    *  Improve code performance, quality, robustness and correctness
    *  Allow ${x:n} where n is an identifier (veedeeh)
    *  Permit ‘+’ in alias names, but not leading (Aleksey Cheusov)
    *  Fix here strings for $@ (LP#1857195), reported by jvdh
    *   \[multiplexd\] Add vi mode PgDn, similar to PgUp doing history search
    *  Build.sh fixup unreliable test -n/\-z
    *   \[multiplexd\] Correct documentation of vi mode @c
    *  Update to UCD 13.0.0
    *  Use nanoseconds in test -nt / \-ot (LP#1855325)

    R57 rolls up bugfixes, with few hard changes:

    *   \[gecko2\] Update operating environment reporting for the Macintosh
    *   \[Martijn Dekker\] make ${foo#'bar'} in here document behave like ksh93
    *   \[Martijn Dekker\] quote empty strings for re-entry into shell
    *  Improve documentation, especially for tty states
    *  Protect against entering line editing with bad saved tty state
    *  Fix set -o allexport for arrays (which we apparently do)
    *  Handle [lseek(2)](htman/i386/man2/lseek.htm) returning -1 as pointed out by Coverity Scan
    *  Fix left-padding UTF-8 strings
    *  Fix using the “-m” flag on the command line
    *  Update to UCD 11.0.0
    *   \[multiplexd\] Fix a segfault using ^W during search in Vi mode
    *  Fix an error message; add a test for controlling tty
    *  Permit unsetting LINES and COLUMNS, for those who need it
    *  Fix manpage bug (RedHat BZ#1612173)
    *  Minor spelling cleanup
    *  Unbreak high-bit7 (nōn-ASCII) heredoc separators (LP#1779179)
    *  Allow dumping high-bit7-char-containing strings in DEBUG mode
    *  Add some testcases for behaviour questions popped up in IRC
    *  Trick a GCC warning, to make up for it ignoring [lint(1)](htman/i386/man1/lint.htm) hints
    *  Add O\_MAYEXEC support for CLIP OS
    *  Make dup-to-self with ksh-style fd≥3 closing work; catern via IRC
    *  Add compat glue for newer GNU groff mdoc to the manpages
    *  Trigger EXIT trap after single-command subshells (Debian #910276)
    *  Document set -eo pipefail caveat (LP#1804504)
    *  Fix MKSH\_EARLY\_LOCALE\_TRACKING warning
    *  Document that, when your Unix is broken, GIGO applies (LP#1817959)
    *  Improve error message for inaccessible executables (LP#1817789)

    R56c is a bugfix-only release everyone must upgrade to:

    *   \[komh\] Remove redundant OS/2-specific code, clean up others
    *   \[komh, tg\] Fix drive-qualified (absolute and relative) DOS-style path support in realpath functionality, partially other places
    *  Don’t substitute ${ENV:-~/.mkshrc} result again
    *  Improve OS/2 $PATH (et al.) handling, drive-relative paths
    *  Add MKSH\_ENVDIR compile-time option for Jehanne and Plan 9
    *  Limit nesting when parsing malformed code (Debian #878947)
    *  Update wcwidth data with bugfixed script (still Unicode 10; resulting values are identical to glibc git master for extant chars)
    *   \[Dr. Werner Fink\] Raise some time limits in the testsuite
    *   \[Shamar\] Add support for the Jehanne operating system
    *   \[komh\] Set stdin to text mode before executing child processes on OS/2
    *   \[komh\] Pass arguments via a resonse file if executing a child fails
    *   \[Dr. Werner Fink\] Early locale tracking as a compile-time option
    *  Fix regressions introduced with new fast character classes

    R56b is a bugfix-only release everyone should upgrade to:

    *  Reference the FAQ webpage
    *   \[panpo, Riviera\] Fix documentation bug wrt. Esc+Ctrl-L
    *  Fix “0” movement in vi mode
    *  Replace broken libcs’ offsetof macro with MirBSD’s

    R56 is a bugfix release with some experimental fixes:

    *  Do not apply alias name restrictions to hash/tilde tracking
    *  Restore ‘.’, ‘:’ and ‘\[’ in alias names (“\[\[” is still forbidden)
    *  Fix accidentally defanged $PATHSEP test
    *  On ^C (INTR and QUIT edchars), shove edit line into history
    *   \[iSKUNK, tg\] Begin porting to z/OS using EBCDIC encoding, incomplete
    *  Redo fast character classes code, adding POSIX and other helpers
    *  bind parses backslash-escaped ‘^’ (and ‘\\’) as escaped
    *  Building with \-DMKSH\_ASSUME\_UTF8=0 no longer causes a known failure in the testsuite
    *  New test.sh option -U to pass a UTF-8 locale to use in the tests
    *  [re\_format(7)](htman/i386/man7/re_format.htm) BSD: \[\[ $x = \*\[\[:\\<:\]\]foo\[\[:\\>:\]\]\* \]\]
    *  Use Config in check.pl only if it exists
    *  New matching code for bracket expressions, full POSIX (8bit)
    *   \[komh\] Exclude FAT/HPFS/NTFS-unsafe tests on OS/2 (and Cygwin/MSYS)
    *  Update to Unicode 10.0.0
    *  Make readonly idempotent
    *  When truncating the persistent history, do not change the underlying file, do all operations on the locked one; do not stop using the history _at all_ if it has been truncated
    *  Turn off UTF-8 mode upon turning on POSIX mode
    *   \[Martijn Dekker, Geoff Clare, many on the Austin list, tg\] In POSIX mode, make the exec builtin force a $PATH search plus execve
    *  Fix GCC 7, Coverity Scan warnings
    *  Track background process PIDs even interactive
    *  Always expose mksh’s hexdump shell function; speed it up by working on the input in chunks; use character classes to make it EBCDIC safe
    *  Revamp dot.mkshrc default editor selection mechanism

    R55 is mostly a feature release with summary bugfixes:

    *   \[komh\] Fix OS/2 search\_access() and UNC path logic
    *  Undocument [printf(1)](htman/i386/man1/printf.htm) to avoid user confusion
    *   \[Jean Delvare, tg\] Fix printf builtin -R option
    *  Make ${var@x}, unknown x, fail (thanks izabera)
    *  ${var=x} must evaluate x in scalar context (10x Martijn Dekker)
    *  Fixup relation between lksh and mksh, reduce delta
    *  Improve manpage display; add OS/2 $PATH FAQ
    *   \[Jean Delvare\] Fix bugs in manpage
    *  Review tilde expansion, removing “odd use of KEEPASN” and introduce POSIX “declaration utility” concept; wait isn’t one
    *  Add \\builtin utility, declaration utility forwarder
    *  Make $'\\xz' expand to xz, not \\0
    *  Use fixed string pooling (requires the above change in host mksh)
    *  POSIX declaration commands can have varassign and redirections
    *   \[Martijn Dekker\] Add typeset -g, replacing homegrown “global”
    *   \[Harvey-OS\] Disable NOPROSPECTOFWORK, APEX is reportedly fixed now
    *  Display ulimit -a output with flags; improve Haiku
    *  Drop old let\] hack, use \\builtin internally
    *  Fix padding in Lb64encode in dot.mkshrc
    *  Move FAQ content to a separate, new FAQ section in the manpage
    *  Add new standard variable PATHSEP (‘:’, ‘;’ on OS/2)
    *   \[Martijn Dekker\] Fix LINENO in eval and alias
    *   \[komh\] Fix “\\builtin” on OS/2
    *  Improve (internal) character classes code for speed
    *  Fix: the underscore is no drive letter
    *  No longer hard-disable persistent history support in lksh
    *  Introduce build flag \-T for enabling “textmode” on OS/2 (supporting CR+LF line endings, but incompatible with mksh proper)
    *  Merge [mksh-os2](https://github.com/komh/mksh-os2)
    *  Permit changing $OS2\_SHELL during a running shell
    *  Fix multibyte handling in ^R (Emacs search-history)
    *  Allow “typeset -p arrname\[2\]” to work
    *  Make some error messages more consistent
    *  Disable UTF-8 detection code for OS/2 as unrealistic
    *  Limit alias name chars to POSIX plus non-leading ‘-’
    *  Expand aliases at COMSUB parse time
    *  Make “typeset -f” output alias-resistent
    *  Permit “eval break” and “eval continue”
    *  Make \-masm=intel safe on i386
    *  Disambiguate $((…)) vs. $((…)…) in “typeset -f” output
    *   \[Jean Delvare\] Clarify the effect of exit and return in a subshell
    *  Simplify compile-time asserts and make them actually compile-time
    *  Fix ^O in Emacs mode if the line was modified (LP#1675842)
    *  Address Coverity Scan… stuff… now that it builds again
    *   \[Martijn Dekker, tg\] Add test -v
    *  Document set -o posix/sh completely

    R54 is a bugfix release with moderate new features:

    *  Simplify and improve code and manual page
    *  Try GCC 5’s new \-malign-data=abi
    *  Allow interrupting builtin cat even on fast devices (LP#1616692)
    *  Update to Unicode 9.0.0
    *   \[Andreas Buschka\] Correct English spelling
    *  Handle set -e\-related error propagation in || and && constructs correctly
    *  Initialise memory for RNG even when not targeting Valgrind
    *  Shrink binary size
    *   \[Brian Callahan\] Improve support for the contemporary pcc compiler
    *  Fix side effects with lazy evaluation; spotted by ormaaj
    *  New flags -c (columnise), -l, -N for the print builtin
    *   \[Larry Hynes\] Fix English, spelling mistakes, typos in the manpage
    *  Return 128+SIGALRM if read -t times out, like GNU bash
    *   \[Martijn Dekker\] Install both manpages from Build.sh
    *   \[Martijn Dekker\] Document case changes are ASCII-only
    *   \[Ronald G. Minnich, Elbing Miss, Álvaro Jurado, tg\] Begin porting to Harvey-OS and APEX (similar to Plan 9 and APE)
    *   \[KO Myung-Hun\] More infrastructure for the OS/2 (EMX, KLIBC) port

    R53a is a snapshot/feature release:

    *   \[lintian\] Fix spelling
    *  Unbreak multi-line command history broken by history flush
    *  Fix redefining POSIX functions that were Korn functions before
    *  Fix bounds checks in Vi editing mode
    *  Handle combining characters at end of string or output correctly
    *  Fix ${!#} ${!?} ${!-} (POSIX, prompted by izabera)
    *  Fix shf.c-internal buffer overread on printing digits
    *   \[J�rg\] Fix a typo in the testsuite
    *   \[arekm\] Increase default edit line size (unless MKSH\_SMALL)
    *  Improve description of Emacs mode keybindings, especially ^U
    *  Abort read builtin in case of [read(2)](htman/i386/man2/read.htm) errors
    *  Fix most of the ambiguous corner cases related to ${\[pfx\]var\[op\[word\]\]} (${@:-1} still unsupported)
    *   \[carstenh\] Contribute some more testsuite coverage
    *  WDS\_TPUTS now emits QCHAR newline reentrant-safe
    *  Fix var=<< implementation (LP#1380389)
    *  Make XSI [test(1)](htman/i386/man1/test.htm) extensions behave as if they were POSIX
    *  Add $(<<<x) and $(<<EOF…) implementation
    *  Lower minimum screen size accepted as “sane” from the OS to 4×2
    *  Simplify tilde-expanded parameters
    *  Fix default PS1 for substring matches
    *  Apply defer-builtin-with-arguments logic to realpath builtin
    *  Rework string pooling (own vs. compiler’s) (LP#1580348)
    *  Feature: print -A, prints arguments as characters
    *  Replace <<< and \>>> as [ROL](wtf.cgi?ROL) and ROR operators with their new ^< and ^> spelling as per [this proposal](http://david.tribble.com/text/c0xrot.htm)
    *  Clear-to-EOL under tmux to work around its anti-feature
    *  Remove support for using file descriptors with more than a single digit, in preparation for named file descriptors
    *  Correct, but simplify (at the potential cost of more tty I/O than strictly necessary, though never redundant and (probably) not more than before when it was miscalculated), line clearing and redrawing
    *   \[slagtc, tg\] Implement new evaluate-region editing command Esc+Ctrl-E
    *  Prefer external rename utility over the recovery builtin
    *  Remove redundant full-line redraws
    *  Fix errorlevel of ‘.’ (“dot” special builtin) when the sourced script does not run any commands, for POSIX compliance
    *  Refactor op tokens and edchars to shave off some more bytes
    *  Fix some bugs in the manpage and some occasional/minor code bugs
    *  Mark tests requiring new perl as !need-pass
    *  Add $KSH\_MATCH and, to make it usable, ${foo@/bar/baz}
    *  Fix bogus patch from OpenBSD: only NULL the global source in unwind when actually reclaiming its Area
    *   \[izabera\] Mention in the manpage that integer bases go up to 36
    *   \[Natureshadow\] Fix /= operator broken during refactoring

    R52c is a bugfix-only release:

    *  Shave 200 bytes off .text by revisiting string pooling
    *  Fix manpage for ditroff on Schillix
    *  Use sed 1q instead of unportable [head(1)](htman/i386/man1/head.htm)
    *  Implement underrun debugging tool for area-based memory allocator
    *  Fix history underrun when first interactive command is entered
    *  Do not misinterpret “${0/}” as “${0//”, fixes segfault
    *  Fix display problems with special parameters
    *  Catch attempt to trim $\* and $@ with ?, fixes segfault (Todd Miller did this in 2004 for ${x\[\*\]} already, so just sync)
    *   \[Martijn Dekker\] Fix “command -p” with -Vv to behave as POSIX requires
    *  Fix recusive parser with active heredocs
    *  Flush even syntax-failing or interrupted commands to history
    *  Fix invalid memory access for “'\\0'” in arithmetics
    *  Explicitly reserve SIGEXIT and SIGERR for ksh
    *  Catch missing here documents at EOF even under “set -n”
    *   \[kre, tg\] Document Austin#1015 handling (not considered a violation)
    *  Fix buffer overread for empty nameref targets
    *  Fix warnings pointed out by latest Debian gcc-snapshot
    *  Document upcoming set +o changes
    *   \[Martijn Dekker\] Expand testsuite for command/whence

    R52b is a strongly recommended bugfix-only release:

    *  Recognise ksh93 compiled scripts and LZIP compressed files as binary (i.e. to not run as mksh plaintext script)
    *  Document that we will implement locale tracking later
    *  Add EEXIST to failback [strerror(3)](htman/i386/man3/strerror.htm)
    *   \[jilles\] Make set -C; :>foo race-free
    *  Don’t use unset in portable build script
    *  Plug warning on GNU/kFreeBSD, GNU/Hurd
    *  Document read -a resets the integer base
    *   \[J�rg\] Fix manpage: time is not a builtin but a reserved word
    *   \[J�rg, tg\] Make exit (and return) eat \-1
    *  parse “$( (( … ) … ) … )” correctly (LP#1532621), Jan Palus
    *  reduce memory footprint by [free(3)](htman/i386/man3/free.htm)ing more aggressively
    *  fix buffer overrun (LP#1533394), bugreport by izabera
    *  correctly handle nested ADELIM parsing (LP#1453827), Teckids
    *  permit “read -A/-a arr\[idx\]” as long as only one element is read; fix corruption of array indicēs with this construct (LP#1533396), izabera
    *  Sanitise OS-provided signal number in even more places
    *  As requested by J�rg, be clear manpage advice is for mksh
    *  Revert (as it was a regression) POSIX bugfix from R52/2005 related to accent gravis-style command substitution until POSIX decides either way
    *  Handle export et al. after command (Austin#351)
    *  Catch EPIPE in built-in cat and return as SIGPIPE (LP#1532621)
    *  Fix errno in print/echo builtin; optimise that and unbksl
    *  Update documentation, point out POSIX violation (Austin#1015)

    R52 is a strongly recommended bugfix release:

    *   \[\_0bitcount\] Move moving external link from [mksh(1)](htman/i386/man1/mksh.htm) to the [#ksh channel homepage](ksh-chan.htm) linked therein
    *  Make setenv “set -u”-safe and fix when invoked with no args
    *  Make “typeset -f” output reentrant if name is a reserved word
    *   \[oksh\] Zero-pad seconds in “time” output to align columns
    *  Check signals and errorlevels from OS to be within bounds
    *   \[komh, tg\] Quote and document ‘;’ as PATH separator in some places
    *   \[oksh, tg\] Simplify code to call afree() even if arg is NULL
    *  Fix tree-printing and reentrancy of multiple here documents
    *  Work around LP#1030581 by permitting exactly one space after
    *  Code quality work, cleanups
    *  New code for here documents/strings with several bugfixes
    *  Stop using [issetugid(2)](htman/i386/man2/issetugid.htm) for ±p checks, wrong tool for the job
    *  Reintroduce some -o posix changes lost in 2005, plus fixes
    *  Make “source” into a built-in command
    *  Drop “stop” alias, [lksh(1)](htman/i386/man1/lksh.htm) functionality to auto-unalias
    *  Fix \\u0000 ignored in $'…' and print
    *  Improve portability of Build.sh
    *   \[Jilles Tjoelker\] Improve portability of testsuite
    *  Fix tilde expansion for some substitutions (izabera, Chet, Geoff)
    *  Improve reparsing of ((…) |…) as ( (…) |…)
    *   \[Martijn Dekker\] Fix [test(1)](htman/i386/man1/test.htm) not returning evaluation errors
    *  Fix ${\*:+x} constructs (carstenh)
    *  Make (( … )) into a compound command (ormaaj)
    *  Repair a few parameter substitution expansion mistakes

    R51 is a strongly recommended feature release:

    *  OpenBSD sync: handle integer base out of band like ksh93 does
    *  Protect standard code (predefined aliases, internal code, aliases and functions in dot.mkshrc) from being overridden by aliases and, in some cases, shell functions (i.e. permit overriding but ignore it)
    *  Implement GNU bash’s enable for dot.mkshrc using magic aliases to redirect the builtins to external utilities; this differs from GNU bash in that enable takes precedence over functions
    *  Move unaliasing an identifier when defining a POSIX-style function with the same name into lksh, as compatibility kludge
    *  Korn shell style functions now have locally scoped shell options
    *  Change some ASCII-isms to be EBCDIC-aware or pluggable
    *  Mention lksh build instructions on manpage and website
    *  Overhaul signal handling; support new POSIX NSIG\_MAX, add [sysconf(\_SC\_NSIG)](https://www.austingroupbugs.net/view.php?id=741) as a later TODO item
    *  Fix signal bounds (1 ≤ _signum_ < NSIG)
    *  Improve manual pages, especially wrt. standards compliance
    *  Initial EBCDIC work for dot.mkshrc
    *  Add list of z/OS signals to Build.sh
    *  Work around the [sh(1)](htman/i386/man1/sh.htm) backslash-newline problem by moving the code triggering it out of \*.opt and into the consumers
    *   \[colona\] Bind another well-known ANSI Del key in the Emacs mode
    *  Fix ${foo/\*/x} pattern checks, spotted by izabera
    *   \[carstenh\] Fix error output of cd function in dot.mkshrc
    *  read partial returns in \-N and timeout cases
    *  Fix $LINENO inside PS1; spotted by carstenh
    *  Ensure correct padding of at least 2 spaces in print\_columns
    *  Note [issues with nested complex parameter expansions](https://bugs.launchpad.net/bugs/1453827) and follow-up bugfixes to expect
    *   \[OpenBSD\] Some language fixes in documentation; comments
    *  Reimplement multi-line command history (Debian #783978) + fixes
    *   \[Martijn Dekker\] Fix command -v for “shell reserved words”
    *  In dot.mkshrc make use of latest feature: local options
    *  Fix ""$@ to emit a word
    *  Change [cat(1)](htman/i386/man1/cat.htm) hack to look first and not ignore builtin
    *   \[KO Myung-Hun\] Begin porting mksh to OS/2
    *   \[komh, tg\] Some generic minor bugfixes from OS/2 porting
    *  Document [mknod(8)](htman/i386/man8/mknod.htm) isn’t normally part of [mksh(1)](htman/i386/man1/mksh.htm)
    *  Quote arguments to : in build/test scripts as well
    *  Add [cat(1)](htman/i386/man1/cat.htm) hack for [printf(1)](htman/i386/man1/printf.htm)\-as-builtin: always prefer external
    *  Explicitly use binary mode for any and all file I/O in stock mksh
    *   \[Ilya Zakharevich\] Use termio, not [termios(4)](htman/i386/man4/termios.htm), on OS/2
    *  Set edchars to sane BSD defaults if any are NUL
    *  Implement support for PC scancodes in Vi and Emacs editing mode
    *   \[komh\] OS/2 uses ‘;’ as PATH separator plus support drive letters

    Changes in the current (unreleased) R50-stable branch:

    *  Correct some mistakes in the manual page
    *  Fix a bug in the testsuite driver, spotted on EBCDIC systems

    R50f is a **required** security and bugfix release:

    *  Add a patch marker for vendor patch versioning to mksh.1
    *  SECURITY: make unset HISTFILE actually work
    *  Document some more issues with the current history code
    *  Remove some unused code
    *  RCSID-only sync with OpenBSD, for bogus and irrelevant changes
    *  Also disable field splitting for alias 'local=\\typeset'
    *  Fix read -n-1 to not be identical to read -N-1
    *  Several fixes and improvements to [lksh(1)](htman/i386/man1/lksh.htm) and [mksh(1)](htman/i386/man1/mksh.htm) manpages
    *  More code (int → size\_t), comment and testsuite fixes
    *  Make dot.mkshrc more robust (LP#1441853)
    *  Fix issues with IFS='\\' read, found by edualbus
    *   \[enh, tg\] Fix integer overflows related to file descriptor parsing, found by Pawel Wylecial (LP#1440685); reduce memory usage for I/O redirs
    *  Document in the manpage how to set ±U according to [the current locale settings](http://article.gmane.org/gmane.os.miros.mksh/606) via LANG/LC\_\* parameters (cf. Debian #782225)
    *   \[igli, tg\] Some code cleanup and restructuring
    *  Handle number parsing and storing more carefully

    R50e is a **required** bugfix release:

    *  Add more tests detailing behaviour difference from GNU bash
    *  Introduce a memory leak for x=<< fixing use of freed memory instead, bug tracked as LP#1380389 still live
    *  Add x+=<< parallel to x=<<
    *  POSIX “command” loses builtin special-ness
    *  Fix LP#1381965 and LP#1381993 (more field splitting)
    *   \[jilles\] Update location of FreeBSD testsuite for [test(1)](htman/i386/man1/test.htm)
    *   \[Martin Natano\] Remove dead NULL elements from Emacs keybindings
    *  Change several testcases for $\*/$@ expansion with/without quotes to expected-fail, with even more to come ☹
    *  Fix miscalculating required memory for encoding the double-quoted parts of a here document or here string delimiter, leading to a buffer overflow; discovered by zacts from IRC
    *   \[RT\] Rename a function conflicting with a MacRelix system header
    *  Use size\_t (and ssize\_t) consistently, stop using ptrdiff\_t; fixes some arithmetics and S/390 bugs
    *  Remove old workarounds for Clang 3.2 scan-build
    *  Remove all Clang/Coverity assertions, making room for new checks
    *  Fix NSIG generation on Debian sid gcc-snapshot
    *  Make a testcase not fail in a corner case
    *  Fix issues detected by GCC’s new sanitisers: data type of a value to be shifted constantly must be unsigned (what not, in C…); shebang check array accesses are always unsigned char
    *  Be _even_ more explicit wrt. POSIX in the manpage
    *  Fix shebang / file magic decoding
    *  More int → bool conversion
    *  Let Build.sh be run by GNU bash 1.12.1 (Slackware 1.01)
    *   \[Stéphane Chazelas, tg\] Fix here string parsing issue
    *  Point out more future changes in the manpage
    *  Call [setgid(2)](htman/i386/man2/setgid.htm), [setegid(2)](htman/i386/man2/setegid.htm), [setuid(2)](htman/i386/man2/setuid.htm) before [seteuid(2)](htman/i386/man2/seteuid.htm)
    *  Fix spurious empty line after ENOENT “whence -v”, found by Ypnose
    *  Optimise dot.mkshrc and modernise it a bit
    *  Use MAXPATHLEN from <sys/param.h> for PATH\_MAX fallback
    *  Some code cleanup and warnings fixes
    *  Add options \-a argv0 and \-c to exec
    *   \[jsg\] Prevent use-after-free when hitting multiple errors unwinding
    *  Fix use of $\* and $@ in scalar context: within \[\[ … \]\] and after case (spotted by Stéphane Chazelas) and in here documents (spotted by tg@); fix here document expansion
    *  Unbreak when $@ shares double quotes with others
    *  Fix set -x in PS4 expansion infinite loop

    R50d is a **required** bugfix release:

    *   \[Goodbox\] Fix NULL pointer dereference on “unset x; nameref x”
    *  Fix severe regression in field splitting (LP#1378208)
    *  Add a warning about not using tainted user input (including from the [environ(7)](htman/i386/man7/environ.htm)ment) in arithmetics, until Stéphane writes it up nicely

    R50c is a **security fix** release:

    *  Know more rare signals when generating sys\_signame\[\] replacement
    *  OpenBSD sync (mostly RCSID only)
    *  Document HISTSIZE limit; found by luigi\_345 on IRC
    *   \[zacts\] Fix link to Debian .mkshrc
    *  Cease exporting $RANDOM (Debian #760857)
    *  Fix C99 compatibility
    *  Work around klibc bug causing a coredump (Debian #763842)
    *  Use [issetugid(2)](htman/i386/man2/issetugid.htm) as additional check if we are FPRIVILEGED
    *  SECURITY: do not permit += from environment
    *  Fix more field splitting bugs reported by Stephane Chazelas and mikeserv; document current status wrt. ambiguous ones as testcases too

    R50b is a recommended bugfix release:

    *   \[Ypnose\] Fix operator description in the manpage
    *  Change all mention of “eglibc” to “glibc”, it is merged back
    *   \[Colona\] Fix rare infinite loop with invalid UTF-8 in the edit buffer
    *  Make more clear when a shell is interactive in the manpage
    *  Document that % is a symmetric remainder operation, and how to get a mathematical modulus from it, in the manpage
    *  Make the [cat(1)](htman/i386/man1/cat.htm) builtin also interruptible in the write loop, not just in the read loop, and avoid it getting SIGPIPE in the smores function in dot.mkshrc by terminating cat upon user quit
    *  Make some comments match the code, after jaredy from obsd changed IFS split handling
    *  Fix some IFS-related mistakes in the manual page
    *  Document another issue as known-to-fail test IFS-subst-3
    *  Improve check.pl output in some cases
    *  Relax overzealous nameref RHS checks

    R50 is a recommended bugfix release:

    *  Fix initial IFS whitespace not being ignored when expanding
    *  MKSH\_BINSHREDUCED no longer mistakenly enables brace expansion
    *  Explain more clearly Vi input mode limitations in the manpage
    *  Improve error reporting of the check.pl script (which needs a maintainer since I don’t speak any [perl(1)](htman/i386/man1/perl.htm), really), for lewellyn
    *  Use $TMPDIR in test.sh for scratch space
    *  Check that the scratch space is not mounted noexec
    *   \[pekster, jilles, tg\] Use [termcap(5)](htman/i386/man5/termcap.htm) names, not [terminfo(5)](htman/i386/man5/terminfo.htm) names, in [tput(1)](htman/i386/man1/tput.htm) examples, for improved portability (e.g. to MidnightBSD)
    *  Avoid C99 Undefined Behaviour in mirtoconf LFS test (inspired by Debian #742780)
    *  Fix ${!foo} for when foo is unset
    *  Improve nameref error checking (LP#1277691)
    *  Fix readonly bypass found by Bert Münnich
    *   \[Ryan Schmidt\] Improved system reporting for Mac OS X
    *   \[nDuff\] Explain better \[\[ extglob handling in the manpage
    *  Remove arr=(\[index\]=value) syntax due to regressions
    *  IFS-split arithmetic expansions as per POSIX 201x
    *   \[OpenBSD\] Add more detailed Authors section to manpage
    *  Fix set ±p issue for good: drop privs unless requested
    *  Improve signal handling and use a more canonical probing order
    *  Fix return values $? and ${PIPESTATUS\[\*\]} interaction with set -o pipefail and COMSUBs
    *   \[enh\] Detect ENOEXEC ELF files and use a less confusing error message
    *  Update to Unicode 7.0.0
    *  Shut up valgrind in the $RANDOM code
    *  Use -fstack-protector-strong in favour of -fstack-protector-all
    *  Fix access-after-free crash spotted by Enjolras via IRC

    R49 is a recommended bugfix release:

    *  dot.mkshrc: fix two issues with the cd wrapper
    *  Unbreak set +p (wider issue still to be addressed)
    *   \[Steffen Daode Nurpmeso\] Use WCONTINUED with [waitpid(2)](htman/i386/man2/waitpid.htm)
    *   \[millert\] Add proper suspend builtin handling [tty(4)](htman/i386/man4/tty.htm) and [setpgrp(2)](htman/i386/man2/setpgrp.htm)
    *  Sanitise and slightly optimise control character handling
    *  Add O\_BINARY to all [open(2)](htman/i386/man2/open.htm) calls for OS/2 kLIBC support
    *  Generate option strings for shell, set, ulimit at compile time
    *   \[Steffen Daode Nurpmeso\] Drop ISTRIP [termios(4)](htman/i386/man4/termios.htm) mode
    *  Mention negative history numbers, octals in the manpage
    *  Make check.pl work with Perl < 5.6.1 again
    *  Detect [getsid(2)](htman/i386/man2/getsid.htm) and skip the oksh suspend builtin otherwise
    *  Document that set -o noclobber is unsafe for tempfiles
    *  Update to Unicode 6.3.0
    *   \[RT\] Restore some portability
    *  Fix parsing positional argument variable names
    *  Sprinkle a few \_\_attribute\_\_((\_\_pure\_\_)); fix warnings
    *  Fix build on OSX: always use our wcwidth code; only use our [strlcpy(3)](htman/i386/man3/strlcpy.htm) code if the OE doesn’t provide one (prompted by jonthn on IRC)
    *  Optimise sh -c to exec even in MKSH\_SMALL
    *  Use new BAFH for hashing

    R48b is a minor bugfix update:

    *  Fix display issue with multi-line prompts and SIGWINCH

    R48 is a small but important bugfix update:

    *  dot.mkshrc: unbreak [hd(1)](htman/i386/man1/hd.htm) function in UTF-8 mode
    *   \[Jens Staal, tg\] Improve buildability on Plan 9 and support kencc
    *  Clean up and improve build process and testsuite
    *   \[Michael Langguth\] Add multi-layer ICO file from mksh/Win32
    *  Fix interactive shell exiting on ^C or syntax error when the EXIT pseudo-signal trap was set (to anything)
    *  Display longer command excerpts in job control
    *  Rewrite Emacs mode display window sliding calculation code
    *  dot.mkshrc: “doch” now keeps standard input
    *  Reduce memory usage and improve comments and documentation
