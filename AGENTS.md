# Building NSS project

This repository requires additional dependencies and external sources to build.

## Dependencies

Install system packages (example for Debian/Ubuntu):

```bash
sudo apt update
sudo apt install mercurial git ninja-build python3-pip
```

Install `gyp-next` using pip:

```bash
python3 -m pip install --user gyp-next
```

Ensure `$HOME/.local/bin` is in your `PATH` so that the `gyp` command is available.

## Fetch NSPR

NSS depends on the NSPR library. Clone it as a sibling directory to `nss`:

```bash
hg clone https://hg.mozilla.org/projects/nspr ../nspr
```

## Building

Run the build script from the `nss` directory. This script builds NSPR and NSS using gyp and ninja:

```bash
cd nss
./build.sh
```

The script places build artifacts in `../dist`. Run `./build.sh --help` for options. Alternatively, the legacy make system can be invoked with `make nss_build_all`.
