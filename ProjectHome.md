# Update Dec 2011 #

The source code is no longer public. Future versions of leaf may be published at leafsr.com






Leaf is an extendable ELF static analysis and debugging tool written in C. Leaf was designed for security research of open source software. Leaf contains all the functionality needed to combine both static and dynamic analysis techniques into a powerful analysis platform. Leaf also includes a plugin interface for expanding its capabilities. It works with 32-bit x86 ELF objects for Linux, BSD and Sun Solaris platforms (other x86 ELF objects from other OS's may also work). 64bit support is in development.

The core engine correlates many things such as code and data cross references, symbols and code relocations. By itself, Leaf is nothing special. The plugin framework for developing quick information extracting tools is what adds value. The code is currently in a beta stage and is available through the downloads tab above. I have also provided a few example plugins such as a hit tracer which uses Leaf's debugging API, a plugin that embeds the Ruby interpreter, a plugin that searches data sections for embedded files using libmagic, and some other basic examples.

Leaf was written to run on x86 Linux platforms. The debug API is strictly Ptrace and still needs a few changes in order to run on BSD.

Leaf **requires** the latest stable git branch of the udis86 library. You can download it here http://udis86.sourceforge.net/


---


# Updates #

**Version 1.0 October/2009** - I am finally changing the versioning scheme to something more sane! The list of changes is huge, mostly under-the-hood stuff that should make Leaf more usable. Also wrapped the debug API using LeafRub. Now you can write hit tracers in just a few lines of Ruby. New command line option -u for specifying exactly which plugins should be loaded. Please see doc/changelog for a complete list of changes.

**Please refer to the Changelog for older changes**