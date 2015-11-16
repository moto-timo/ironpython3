# IronPython 3
[Official Website](http://ironpython.net)

IronPython is an open-source implementation of the Python programming language which
is tightly integrated with the .NET Framework. IronPython can use the .NET Framework
and Python libraries, and other .NET languages can use Python code just as easily.

IronPython 3 targets Python 3, including the re-organized standard library, Unicode
strings, and all of the other new features.

## Current project status

Continuous Integration is provided by [Travis-CI][travis] and [AppVeyor][appveyor].

|  Windows   |  Linux/Mono  |
|  :-------: |  :--------:  |
|  [![Build status][win-badge]][win-project] | [![Build Status][mono-badge]][mono-project] |

Static analysis is provided by [Coverity][coverity]. Code coverage is provided by [Coveralls.io][coveralls].

| Static Analysis | Code Coverage |
| :-------------: | :-----------: |
| [![Static Analysis][coverity-badge]][coverity-project] | [![Coverage Status][coveralls-badge]][coveralls-project] |

[travis]: https://travis-ci.org/
[appveyor]: http://appveyor.com/
[coverity]: https://scan.coverity.com/
[coveralls]: https://coveralls.io/

[win-project]: https://ci.appveyor.com/project/moto-timo/ironpython3
[win-badge]: https://ci.appveyor.com/api/projects/status/jqby7nc3oioqo9a2?svg=true
[mono-project]: https://travis-ci.org/moto-timo/ironpython
[mono-badge]: https://travis-ci.org/moto-timo/ironpython3.svg?branch=continuous_integration

[coverity-project]: https://scan.coverity.com/projects/7042
[coverity-badge]: https://scan.coverity.com/projects/7042/badge.svg

[coveralls-project]: https://coveralls.io/github/moto-timo/ironpython3?branch=master
[coveralls-badge]: https://coveralls.io/repos/moto-timo/ironpython3/badge.svg?branch=continuous_integration&service=github

Thanks to the [libgit2sharp](https://github.com/libgit2/libgit2sharp) project for a great [example](https://raw.githubusercontent.com/libgit2/libgit2sharp/vNext/README.md) of embedding the above badges.

## Installation
Builds of IronPython 3 are not yet provided.

## Build
On Windows machines, start a Visual Studio command prompt and type:

    > make
    
On Unix machines, make sure Mono is installed and in the PATH, and type:

    $ make

Since the main development is on Windows, Mono bugs may inadvertantly be introduced
- please report them!

## Supported Platforms
IronPython 3 currently builds for .NET 3.5 SP1, .NET 4.0, and .NET 4.5. The main
platform will be .NET 4.5, but .NET 4.0, 3.5, and Silverlight 5 will still be supported
for embedding.

Support for Android, Windows 8 Store Apps (Metro), Window Phone 8, and iOS are also
planned (in roughly that order).

## Custom DLR
If you need to make changes to the DLR, you can point IronPython at your local DLR using
`set-dlr-source`:

    set-dlr-source ..\dlr

(Windows)

    ./set-dlr-source.sh ../dlr

(Unix)

After making DLR changes, commit them, update the version, and release an updated NuGet.
Then, update the `DlrVersion` property in `CurrentVersion.props`.

