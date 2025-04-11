[![CI Status](https://github.com/timfel/paatch/actions/workflows/workflow.yml/badge.svg)](https://github.com/timfel/paatch/actions/workflows/workflow.yml)
[![PyPI](https://img.shields.io/pypi/v/paatch)](https://pypi.python.org/pypi/paatch)

## Paatch - parse and apply unified diffs

### Installation and Usage

    pip install paatch
    patch -h

### Why did I fork?

This project is a fork of [python-patch-ng](https://github.com/conan-io/python-patch-ng), which itself is a fork of the original [python-patch](https://github.com/techtonik/python-patch) project.

I needed a tool to apply unified patches with some GNU extensions, ideally in pure Python.
The set of patches I'm interested are the [GraalPy patches](https://github.com/oracle/graalpython/tree/master/graalpython/lib-graalpython/patches).
They apply fine with GNU patch, but the BSD patch utility in macOS chokes on some and getting GNU patch to work on Windows was a bit of hit and miss.
This is also why originally the `python-patch` project was born in the first place:

> In 2008 there was no reliable Windows tool to apply patches,
> and there was no cross-platform solution that could be safely
> run by web server process.
> 
> (UNIX *patch* utility)[http://www.gnu.org/software/patch/] was
> (ported to windows)[http://gnuwin32.sourceforge.net/packages/patch.htm],
> but there were (a couple of bugs)
> [http://www.google.com/search?q=Assertion+failed%3A+hunk%2C+file+patch.c]
> that proved that it can not be run securely in web server process.
> The utility was also hard to tweak without a C compiler, it messed
> badly with LF and CRLF line end differences, and so this project
> was born.
> 
> *patch.py* was meant to be a cross-platoform tool with intuitive
> defaults, taking care of the most problems (e.g. line end
> differences) automatically.

So I added what I needed, and now have a PyPI package I can use to apply GraalPy patches on each of these platforms and they will be applied in the same manner.

### Credits

Reproducing the thanks in the original project:

Alex Stewart
Wladimir J. van der Laan (laanwj)
azasypkin
Philippe Ombredanne
mspncp
Yen Chi Hsuan (@yan12125)

* [LICENSE: UPL](LICENSE)
