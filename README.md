Hi all, this repo is an attempt to get as much software as possible updated from webkit2gtk4.0 to webkit2gtk4.1 on slackware 15.0

The main progress file is webkit2gtk4.0revdeps

This contains the status and what is needed to get the current packages which use webkit2gtk4.0 to use weblit2gtk4.1
The significant change is the switch from soup2 to soup3. As you can't have both libs in a single binary or library, this
is an all or nothing type of change for many projects, and so not one that is wanted to be forced on people if possible,
until slackware 15.1 comes out, at which point, a number of the package maintainers effected already have newer soup3
based packages ready to go, and base support is present.

In otherwords, this is a stop-gap till then for people who need to use packages that have already updated to soup3.
some older libraries have lost project devs, or otherwise been abandonded, and unless there is a patch available, they
are likely to be abandoned here as well.
I've tried where possible to make the build script still work for 4.0, so that script updates can go live on slackbuilds.org
and be more available for those that want or need to tinker.

As the date for release of Slackware (TM) 15.1 is unknown until it happens (although sbo devs do get a bit of a heads up),
this is for that inbetween time. Hopefully a release will be more speedy than the wait from 14.2 to 15.0 :-)

Note: unless you are testing, do not switch to webkit2gtk4.1 unless all the packages you use can be updated. You will have
to rebuild all of the packages.

souppkgchk is a script which will check a package for issues relating to this update, reporting files with dynamic linking
to soup2, soup3, or both (a binary that will not run). It can be used for checking packages that may need work or updating.
