# minibsdiff: a miniature, portable version of bsdiff.

Colin Percival's [bsdiff][] is a popular tool for creating and applying binary
patches to software. This is a stripped down copy of `bsdiff` that's designed
to be portable and reusable as a library in your own software (if you wanted to
say, create your own update system.) Many people end up reusing bsdiff (it's
stable, well-known, small, and has a good license,) but I haven't found a
standalone copy of the library somewhere that I could easily reuse, so I wrote
one.

The main differences:

  * Control/data/extra blocks in the patch output are not `bzip2` compressed.
    You'll have to apply your own compression method. **This means that the
    patches produced by this library are incompatible with those produced by
    the classic bsdiff tool!**

  * The code has been refactored into a reusable API, consisting of a few
    simple functions in `bsdiff.h` and `bspatch.h`.

[travis-ci.org](http://travis-ci.org) results: [![Build Status](https://secure.travis-ci.org/thoughtpolice/minibsdiff.png?branch=master)](http://travis-ci.org/thoughtpolice/minibsdiff)

# Usage

Just include `bsdiff.{c,h}` and `bspatch.{c,h}` in your source tree and you're
ready to go.

This is the entire API:

```c
/* TODO FIXME */
```

For an full example of using the API, see `minibsdiff.c`, which roughly
reimplements the standard `bsdiff/bspatch` in a single tool. You can build the
example application by running `make`.

# Join in

File bugs in the GitHub [issue tracker][].

Master [git repository][gh]:

* `git clone https://github.com/thoughtpolice/minibsdiff.git`

There's also a [BitBucket mirror][bb]:

* `git clone https://bitbucket.org/thoughtpolice/minibsdiff.git`

# Authors

See [AUTHORS.txt](https://raw.github.com/thoughtpolice/minibsdiff/master/AUTHORS.txt).

# License

2-clause BSD. See `LICENSE.txt` for terms of copyright and redistribution.

[bsdiff]: http://www.daemonology.net/bsdiff/
[issue tracker]: http://github.com/thoughtpolice/minibsdiff/issues
[gh]: http://github.com/thoughtpolice/minibsdiff
[bb]: http://bitbucket.org/thoughtpolice/minibsdiff
