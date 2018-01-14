# cint-5.34.00
The last working version of "cint" C/C++ Interpreter, pulled from within "root-5.34.00-patches" 

To compile, supply the path to "libreadline.a", if it is not "/usr/(local)/lib/libreadline.a". For example on the Raspberry Pi:

```
./configure --readlinelib=/usr/lib/arm-linux-gnueabihf/libreadline.a
```

When you run **make** you will get 4 errors, after _cint_ itself has been built, while compiling with _makecint_. Those errors are contained within **fixme.txt**, you are welcome to submit patches.

This version was tested with **GCC-4.9** on Raspbian Jessie (oldstable) on a RPi2, on PipaOS 5. Its was the only version that would build without serious errors. It is the last _tag_ vesrion available from the _root_ project, however other patches may be found before the move to v6.0.0, which uses _cling_.

The newer v6.0.8, although last updated in 2015, does not build with G_NEWSTDHEADERS, and I could not decipher the header death that is rank without that define. That version also looks to only have been tested on Windows, possibly only with Visual C/C++ (not GCC on CygWin), and no longer contains a _configure_ script. The new include structure will not support the older _configure_ script.

The old v5.16.19 will build, also with **GCC-6.1.0**, but it fails seriously when building the core element _gcc3stream_ and a few other components (with the same error).This error was later fixed but no one has updated the CERN CINT page since then (Oct 2007), and I was unable to find the patch commit.


This version will not build with **GCC-6.1.0**, exiting with:

```
tool/rmkdepend/rmkdepend: /usr/lib/arm-linux-gnueabihf/libstdc++.so.6: version `GLIBCXX_3.4.21' not found (required by tool/rmkdepend/rmkdepend)
```

Again, patches are welcome, but please maintain **GCC-4.9** ability to compile.

Jan 2018
paulwratt@github

