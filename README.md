# OpenBSD Ports for the Tor Browser Bundle (TBB) #

These are the OpenBSD ports that correspond to the Tor browser bundle.
They are a work in progress.  Please beware that until we make release
announcements on [our web site](https://torbsd.github.io) you should
be careful using this stuff.  You must be runing OpenBSD -current and
have your ports and src synced up (like I said: running -current).

## Branches and Versions ##

As of 29 July 2015 the `master` branch has release __4.5.3__:

    ff-esr            31.8.0
    torbutton         1.9.2.8
    tor-launcher      0.2.7.5
    noscript          2.6.9.27
    https-everywhere  5.0.5

The `develop` branch is always used to work on the next release.  We
use tags to mark release points that correspond as closely as possible
to TBB releases.  They are marked "-sans-pt" to indicate that
Pluggable Transports (PT) is not yet a part of this set of
ports... working on it...

## Meta Package ##

There is also a meta/tbb package, but in order to use it it needs at
least `/usr/ports/meta/Makefile.inc` dropped in; assuming you have
copied the `meta` and `www` dirs from this repo to
`/usr/ports/mystuff`:

    # cp /usr/ports/meta/Makefile.inc /usr/ports/mystuff/meta/
    # cd /usr/ports/mystuff/meta/tbb
    # make install

YMMV.  I mainly did that for convenience in testing, but it's morally
no different than the `meta/avr` port.

## Play Along at Home ##

I keep notes in [notes.org](notes.org).  You're welcome to look over
my shoulder but then don't be offended by what I say :-) ...  This
work is sometimes irritating; if I'm going to be transparent then I
have to vent transparently sometimes, as well... Also, we've started
using [the GH issue tracker](https://github.com/torbsd/openbsd-ports/issues)
to enumerate (if not organize) what we're working on.

I generally build and test on amd64 first, i386 second.  Testing on
other architectures greatly appreciated.

## Repositories ##

Most of the ports in this repo pull their source tarballs from other
GH [torbsd repositories](https://github.com/torbsd).  This is because
the Tor project chooses not to make source tarballs easily available
for anything except tor itself (their gitian-based build process does
not require them).  Also, the OpenBSD ports system explicitly supports
pointing at GH projects.  I maintain the tags and branches in these
repositories and track changes in the
[tor project's git repositories](https://gitweb.torproject.org).
Where possible I prefer to have ports pull source from some
authoritative download area maintained by the project itself; in the
case of noscript I do this, for example.

## Beware: Experimental Until Otherwise Stated ##

You should be aware that there might be bugs or issues that could
_e.g._ screw over your non-tor `~/.mozilla` directory over if you
aren't careful.  Naturally we try to avoid this but if you want to
play along then be careful: don't run a non-tor-browser at the same
time, make sure you back up all of your precious bits before using
tor-browser (like `~/.mozilla`), etc.  Note that we have sort of
hot-wired the profile root to be `~/.tor-browser` under OpenBSD and
this does appear to work, but until we test it all more thoroughly
_caveat emptor_.  Read the [notes](notes.org) if you're really curious
what's going on or come find me.

## Contact ##

You can get my attention by posting [issues](https://github.com/torbsd/openbsd-ports/issues) to this repository if you
like, or use one of the contact methods mentioned on my
[home page](http://trac.haqistan.net/~attila).

`--attila`
