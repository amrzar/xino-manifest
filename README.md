# xino repo manifest

## Prerequisites

```bash
sudo apt update
sudo apt install repo
```
## Layout produced by `repo sync`

```
<workspace>/
  .repo/
  xino/              # git@github.com:amrzar/xino.git
    build-tools/     # CMake build tree (generated locally)
    tools/           # git@github.com:amrzar/xino-tools.git
    ...other xino sources...
```

## Usage

```bash
repo init -u git@github.com:amrzar/xino-manifest.git -m default.xml
repo sync
```

## Building `xino-tools`

```bash
cmake -S tools -B build-tools -G "Unix Makefiles" \
  -DCMAKE_BUILD_TYPE=Release

cmake --build build-tools  -j$(nproc)
```
