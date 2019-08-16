# ZMQInterface

A plugin for open-ephys enabling the interfacing of [ZeroMQ](http://zeromq.org) clients to open ephys. 

Forked from [Francesco Battaglia's github repository](https://github.com/MemDynLab/ZMQInterface).

The interface exposes all data and events and allows to provide events to the application, enabling the creation of advanced visualization and monitoring add-ons.

The code in the examples under the `python_clients` directory may serve as tutorial for now. Note that the application may be written in any language/platform supporting ZeroMQ.

## Installation Instruction

The original plugin is compatible with the Linux and MacOSX versions of Open Ephys. The plugin was ported to Visual Studio/Windows and updated in 2018-2019 to a current Open Ephys version with modified plugin architecture. Some features were disabled during the process.

### Compile from source code

The Plugin is organized so that it can be compiled as much as possible outside of the main open-ephys source tree. Under Linux, a symlink to the Source/Plugins directory is however necessary. 


To compile, extract in a folder just outside the Open Ephys plugin-GUI source tree
e.g. 

```
$ ls src
plugin-GUI/
ZMQInterface/
etc...
```

The rest of the procedure is system dependent

####Linux 
- edit `build-linux.sh` to change `ZMQ_PREFIX` to the location where ZeroMQ is installed 
- `cd PythonPlugin`
- run `./build-linux.sh`. The Plugin should be copied to the neighboring plugin-GUI source tree. 

####MacOSX

- With a different Python distribution: in the same file, edit `HEADER_SEARCH_PATHS` and `LIBRARY_SEARCH_PATHS` to the proper places so that ZeroMQ may be found. 
- Open `Builds/MacOS/PythonPlugin.xcodeproj` in XCode and compile

####Windows

- Visual Studio 2013 project files provided.
- Expects a `github-plugin-GUI` folder on the same level as the `zmqinterface_oeplugin` with an already compiled `open-ephys.lib`.

### Binary installation 
A binary installation (Linux only for the time being) is provided [here](https://github.com/fpbattaglia/ZMQInterface-linux-binaries)

- Use the Binary-distributed version of Open-Ephys or compile it from source with the Release configuration. 
- Copy PythonPlugin.so to the `plugins` directory, and you are done. 



 



