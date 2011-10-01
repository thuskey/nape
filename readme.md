![](http://deltaluca.me.uk/napelogo.jpg)

# Where to download

Only source code is available here on github. To download pre-built nape you should visit my homepage, with new versions currently being uploaded by version to http://deltaluca.me.uk/napenew with newest version and documentation at http://deltaluca.me.uk/docnew

It may be the case that (possibly non) stable releases will be made here on github first which you can access via traversing to the file, and swapping /blob/ in the path to /raw/ instead.

# Which build to use

For general development purposes ALWAYS use the debug builds; these are not much slower than the release builds but provide you with a large amount of error detection to ensure you're using nape
correctly.

You should only use release builds when you are absolutely sure you have no nape errors, and are releasing a final product. Any uncaught errors will either lead to bad behaviour and/or flash player
exceptions.

If you are one of those lucky people helping me track down bugs, use the assertion builds. Even with the limited information avaiable from .swcs, assertion builds provide much more useful
information to track down a bug.

# compiling from source

Dependancies:

* haxe
* hxcpp (for c++ compilation)
* caxe
* flib (if you want to compile AS3 nape .swcs)
    
flib and caxe may be found from my other github repositories, and may also be compiled from source.

The supplied Makefile should work fine under unix systems, commands will be identical from windows command line.

# haXe compiler flags

for assertion builds; use flags

    -D NAPE_ASSERT --no-inline -debug

if compiling to AS3 nape .swcs you must instead use

    -D NAPE_ASSERT -D NAPE_NO_INLINE

as some inlining (for flib properties) is necessary for a functioning .swc

for debug builds; use no extra flags

for release builds; use flags

    -D NAPE_RELEASE_BUILD

# Pre-build nape

For AS3, you must use the compiled .swcs

For haXe, you 'can' use the hx-src tar, but it's suggested that you should use the compiled .swfs instead using -swf-lib as it will be a lot faster for you on compile times.