# Retro Docker files

This repo have some Dockerfiles with information for Create a development environment for [Devkitpro](https://devkitpro.org/) ARM Development (for GameBoy Advance and Nintendo DS) or SDL2 Linux Development.

This is only for demostration pruposes.

You have 3 folders:

* GBA: create a docker image with devkitpro libraries and tools and generate a volume for compile and generate gba roms.
* NDS: create a docker image with devkitpro libraries and tools and generate a volume for compile and generate nds roms.
* SDL: Create a docker image with SDL2 for linux or using cross compiling with mingw32.

## Build image

```bash
docker build -t <tag> .
```

## Compile and generate Rom

* gba

```bash
docker run --rm -v <path-to-your-makefile>:/src/gba gba
```

* nds

```bash
docker run --rm -v <path-to-your-makefile>:/src/nds nds
```

* sdl

For Linux

```bash
docker run --rm -v <path-to-your-makefile>:/src/sdl2 sdl make all
```

For Windows

```bash
docker run --rm -v <path-to-your-makefile>:/src/sdl2 sdl make game.zip
```

You can find a template or example in the next repositories.

* gba: [https://github.com/devkitPro/gba-examples](https://github.com/devkitPro/gba-examples)

* nds: [https://github.com/devkitPro/nds-examples](https://github.com/devkitPro/nds-examples)

* sdl: [https://github.com/emiliollbb/taller_sdl](https://github.com/emiliollbb/taller_sdl)
