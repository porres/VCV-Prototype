# VCV Prototype

[Pure Data](https://puredata.info) engine for [VCV Rack](https://vcvrack.com/) containing:
- 6 inputs
- 6 outputs
- 6 knobs
- 6 lights (RGB LEDs)
- 6 switches with RGB LEDs

## Build dependencies

Set up your build environment like described here, including the dependencies: https://vcvrack.com/manual/Building

Additionally:

### Windows
```bash
pacman -S mingw-w64-x86_64-premake
```

### Mac
```bash
brew install premake
```

### Ubuntu 16.04+
```bash
sudo apt install premake4
```

### Arch Linux
```bash
sudo pacman -S premake
```

## Build
### Add path to Rack-SDK
```bash
export RACK_DIR=/set/path/to/Rack-SDK/
```

### load submodules
```bash
git submodule update --init --recursive
```

### Make
```bash
make dep
make
```

## Adding a script engine

- You can add scripting language libraries to the build system so it builds with `make dep`.
- Create a `MyEngine.cpp` file (for example) in `src/` with a `ScriptEngine` subclass defining the virtual methods.
- Build and test the plugin.
- Add a few example scripts and tests to `examples/`. These will be included in the plugin package for the user.

## Contributors

- [Wes Milholen](https://grayscale.info/): panel design
- [Andrew Belt](https://github.com/AndrewBelt): host code
- [CHAIR](https://chair.audio) (Clemens Wegener, Max Neupert): libpd
