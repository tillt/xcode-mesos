xcode-mesos
===========

Xcode Workspace for Apache Mesos


## Preconditions

You still need the full build-setup that is used for a "regular" Mesos build, without the Xcode IDE - but only once. For details on these first steps, please consult docs/getting-started.md.

Your first build has to be done using the commandline make as that will trigger further configuration,extraction and patching of the 3rdparty dependencies (e.g. libev etc.).

This Xcode build configuration, for reasons of simplification and speedup, uses prebuilt and installed versions of glog, protobuf and leveldb. Make sure those are installed using homebrew (or MacPorts if you prefer that).


## Using the Mesos Xcode Workspace
1. Clone this project into subfolder of Mesos repository.

	Change working directory

	`$ cd mesos`

	Install this into the mesos folder tree

	`$ git clone https://github.com/lobotomat/xcode-mesos.git`

2. Install available 3rdparty dependencies via Homebrew

	Install glog

	`$ brew install glog`

	Install protobuf

	`$ brew install protobuf`

	Install leveldb

	`$ brew install leveldb`

3. Building Mesos for the first time

	Bootstrap

	`$ ./bootstrap`

	Configure and build

	`$ mkdir build`
	`$ cd build`
	`$ ../configure`
	`$ make -j`

4. Building Mesos using the Xcode IDE

	Open the Mesos Workspace

	`$ open xcode-mesos/mesos.xcworkspace`

	Now select the mesos-all target:

	![Select Scheme](https://github.com/lobotomat/xcode-mesos/blob/master/docs/images/xcode-select-scheme.png?raw=true)

	![All Scheme](https://github.com/lobotomat/xcode-mesos/blob/master/docs/images/xcode-all-scheme.png?raw=true)

	The above scheme builds libprocess, libmesos_no_3rdparty as well as all mesos runnables.


You may now continue editing, running, debugging and maybe even profiling (Instruments, **yes**). Enjoy!


## Questions / Problems

Please use the [github issue tracker](https://github.com/lobotomat/xcode-mesos/issues) for any questions or problems you have with this setup. Do not ask any questions about this within the official Mesos communication channels as the project is not supporting this fork.

