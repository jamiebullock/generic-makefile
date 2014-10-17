Generic Makefile
================

A generic makefile capable of building programs and static or shared libraries

## Features

- Minimal configuration, should just work
- Minimal dependencies, just GNU Make, uname (on Unix), gcc or g++ and ar
- Build an application, static library or shared library
- Include source files from multiple subdirectories

## Usage

The Makefile is designed to be placed at the root of a project directory tree, and executed from this location by typing `make` from a command-line.

In the default configuration, the Makefile is setup as follows:

- The parent directory name is the program name
- C files from the current directory only are compiled

For example, if your files are `test/foo.c` `test/bar.c` then `foo.c` and `bar.c` will be compiled into a program called `test`.

The default options can be overridden by adding a `Make.config` file parallel to the `Makefile`. For example the following `Make.config` will create a static library called libfoo.a by compiling all C++ files in directories `bar` and `baz`:

> SUFFIX = .cpp  
> DIRS = bar baz  
> NAME = foo

The `make debug` target will build a binary file suitable for debugging.

## Credits

This Makefile was influenced by [GenericMakefile](https://github.com/mbcrawfo/GenericMakefile) but is simpler, has fewer dependencies, uses explicit directory specification and supports static and shared libraries

It was also influenced by this [GIST Makefile](https://gist.github.com/mkhl/159461) which gave the idea for library support

