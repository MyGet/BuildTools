# MyGet Build Tools

Out of the box,  [MyGet Build Services](http://www.myget.org) supports building projects that depend on various SDK's and/or test runners (see [supported project types and SDK's](http://docs.myget.org/docs/reference/build-services)).

If for some reason your build requires a different version of a tool or a different test runner, this GitHub repository can be of help. It currently contains the following tools:

* NuGet 2.5, 2.6, 2.7, 2.7.1, 2.7.2, 2.7.3, 2.8.0, 2.8.1, 2.8.5, 2.8.6, 3.1.0, 3.2.0, 3.3.0
* NUnit 2.6.2
* XUnit 1.9.6
* curl 7.40.0 (x86/x64 with openssl, openssh and zlib support)
* remotelens-scp (.NET with SSH/SCP upload support)

## Adding MyGet Build Tools to your build

There are two ways of adding MyGet Build Tools to your build. One is to download only the tools you need from this repository and commit them to your own repository. This enables you to cherry-pick the required tools and not pollute your build with tools you do not need, making the build process faster.

If you do not wish to add the tools into your own repository, you can add the current repository to your own repository as a submodule. This will bring down the tools during a build while they are technically not in your own GitHub repository. To add a submodule, run the following from your repository root (make sure to use the ```https``` URL):

	git submodule add https://github.com/myget/BuildTools.git myget

You can use the tools from the ```myget/tools``` folder in your builds. For example NuGet 2.5 can be used by calling ```myget/tools/nuget/2.5/nuget.exe```.

_Happy packaging!_