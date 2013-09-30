#libphonenumber-compile

##About

This [apache ant](http://ant.apache.org/) build script creates a version of [libphonenumber](https://code.google.com/p/libphonenumber/) with precompiled [google closure library](https://developers.google.com/closure/library/) dependencies.
The advantage of precompiling everything is that you don't need to include the closure library in your project.
In addition to that you don't have to prepare your project to be compatible with the [ClosureBuilder](https://developers.google.com/closure/library/docs/closurebuilder) build process.

##Installation

To run the ant `build.xml` without problems you need the following files:

1. google closure library via `git clone https://code.google.com/p/closure-library/`
2. google closure compiler jar file from [http://dl.google.com/closure-compiler/compiler-latest.zip](http://dl.google.com/closure-compiler/compiler-latest.zip)
3. libphonenumber via `svn checkout http://libphonenumber.googlecode.com/svn/trunk/ libphonenumber-read-only`

If you don't want to change the configuration your setup to build everything should look like this:

    .
    ├── closure-compiler
    │   └── ...
    ├── closure-library
    │   └── ...
    ├── libphonenumber-read-only
    │   └── ...
    ├── libphonenumber-standalone
    │   └── ...
    └── compiler.jar

##Configuration

You can change the paths to the location of the required files and projects. To edit something open the `build.xml`.

- set if the compiled file should use the lite metadata file or not

    <property name="use.metadatalite" value="false" />

- change the libphonenumber directory

    <property name="libphonenumber.dir" value="../libphonenumber-read-only" />

- change the closure-library directory

    <property name="closure-library.dir" value="../closure-library" />

- change the closure-compiler.jar file

    <property name="closure-compiler.jar" value="../compiler.jar" />

- change the compiled javascript filename

    <property name="compiled.name" value="libphonenumber.compiled.js" />

##License

libphonenumber-compile is available under the MIT license. For more information see the `LICENSE` file.
