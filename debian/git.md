# Compiling Git on Debian

## TL;DR;

```
# Install build dependencies
$ sudo apt-get install dh-autoreconf libcurl4-gnutls-dev libexpat1-dev \
      gettext libz-dev libssl-dev

# Prepare source/build directories
$ sudo install -g your-group -o your-user -d /opt/git
$ cd /opt/git

# Get the source code
$ wget https://mirrors.edge.kernel.org/pub/software/scm/git/git-2.25.0.tar.gz
$ tar xvf git-2.25.0.tar.gz
$ cd git-2.25.0

# OR, get the source code using your currently installed Git
$ git clone git://git.kernel.org/pub/scm/git/git.git source
$ cd source
$ git checkout v2.25.0

# Compile
$ autoconf
$ ./configure --prefix=/usr/local
$ make

# Run tests (optional, needs Python 2.7 installed)
$ make test

# Install
$ sudo make install
```

## Preparation

This was attempted on Debian Stretch v9.11 with kernel v4.6.0-1-amd64.

As the time of writing, the official Debian repositories provide Git v2.11.0,
which is definitely usable, but I wanted to run the bleeding edge version of
the most beloved version control system ever (v2.25.0 at the moment).

Time to compile Git!

Luckly, compiling Git is very straight forward. From the official website, you
can find a very useful "[Book]" containing several instructions about Git,
including how to install it from source code.

Git needs the following to compile successfully:

- dh-autoreconf
- libcurl4-gnutls-dev
- libexpat1-dev
- gettext
- libz-dev
- libssl-dev

Having that installed using `apt-get install`, run `autoconf`, to generate
the "configure" files. These are used next:

```
$ ./configure --prefix=/usr/local
```

The `--prefix` part is optional and is actually the default for this version
of Git. I always prefer to have it explicit, as some programs use different
prefixes. It tells where the binaries to be compiled are expected to be
installed (you can't simply move them around).

Next, compile:

```
$ make
```

Optionally, add `-jX` where `X` is the number of parallel jobs used by Make.

After compilation finishes, it's advisable to run the test suite to ensure
everything is functioning correctly. When running in a minimal Docker
container some tests where failing and it took me a while to realize that it
was because of a missing dependency of the tests themselves, that we usually
have locally: Python 2.7. So make sure you have this version of Python
installed before running the tests.

```
$ make test
```

If everything is green, install your fresh new binaries. You need to be root
to do that:

```
$ sudo make install
```

To validate your installation, simply run a git command:

```
$ git --version
git version 2.25.0
```

If you see something like that, enjoy your brand new Git!


[Book]: https://git-scm.com/book/en/v2/Getting-Started-Installing-Git
