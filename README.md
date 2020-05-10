# docker-cpp-devenv
 ![GitHub](https://img.shields.io/github/license/mustafakemalgilor/docker-cpp-devenv) ![Docker Cloud Automated build](https://img.shields.io/docker/cloud/automated/mustafagilor/cpp-devenv) ![Docker Cloud Build Status](https://img.shields.io/docker/cloud/build/mustafagilor/cpp-devenv) ![Docker Image Size (tag)](https://img.shields.io/docker/image-size/mustafagilor/cpp-devenv/latest) ![Docker Pulls](https://img.shields.io/docker/pulls/mustafagilor/cpp-devenv) ![Docker Image Version (latest semver)](https://img.shields.io/docker/v/mustafagilor/cpp-devenv?sort=semver)

Ready-to-use C++ development environment container consist of fully open-source, free software.
## OS

Image is based on `debian:sid` image, since it's bleeding edge and the repositories have the most recent released tool versions available.



## VSCode remote-containers extension support

This image is compatible with Visual Studio Code's Remote-Containers extension. You have several options to use it.

### 1: Use as a base image to .devcontainer/Dockerfile

```dockerfile
FROM mustafagilor:cpp-devenv
```

### 2: Use as main dockerfile in .devcontainer/docker-compose.yml

```yaml
version: '3'
services:
    service-name:
      image: "mustafagilor:cpp-devenv"
```



### GitLab CI support

This image is tested with GitLab CI, and currently used for several projects in production.

```yaml
image: mustafagilor/cpp-devenv:latest
```



## Tools included

### Toolchain

| Debian package name |                         Description                          |    Version    | Available in |
| :-----------------: | :----------------------------------------------------------: | :-----------: | :----------: |
|       gcc-10        |                        GNU C Compiler                        |  >= 10.1.0-1  |   >= v1.0    |
|       g++-10        |                       GNU C++ Compiler                       |  >= 10.1.0-1  |   >= v1.0    |
|  libstdc++-10-dev   |                 GNU Standard C++ Library v3                  |  >= 10.1.0-1  |   >= v1.0    |
|      libc6-dev      |                    GNU Standard C Library                    |   >= 2.30-7   |   >= v1.0    |
|         gdb         |                         GNU Debugger                         |   >= 9.1-3    |   >= v1.0    |
|       llvm-10       |                  LLVM Toolchain, Version 10                  | >= 1:10.0.0-4 |   >= v1.0    |
|       lldb-10       |                  LLVM Debugger, Version 10                   | >= 1:10.0.0-4 |   >= v1.0    |
|      clang-10       | LLVM C, C++, Objective C and Objective C++ Frontend, Version 10s | >= 1:10.0.0-4 |   >= v1.0    |
|      clangd-10      |                    Clang Language Server                     | >= 1:10.0.0-4 |   >= v1.0    |
|    libc++-10-dev    |                  LLVM C++ Standard Library                   | >= 1:10.0.0-4 |   >= v1.0    |

### Build tools

| Debian package name |                     Description                     |    Version    | Available in |
| :-----------------: | :-------------------------------------------------: | :-----------: | :----------: |
|        make         |                      GNU Make                       |  >= 4.2.1-2   |   >= v1.0    |
|     ninja-build     |                 Ninja Build System                  |  >= 1.10.0-1  |   >= v1.0    |
|      autoconf       |         Automatic Configure Script Builder          | >= 2.69-11.1  |   >= v1.0    |
|      automake       |            Automatic Makefile Generator             | >= 1:1.16.2-1 |   >= v1.0    |
|       libtool       |                     GNU libtool                     |  >= 2.4.6-14  |   >= v1.0    |
|         m4          |    GNU m4 macro processor (required by autoconf)    |  >= 1.4.18-4  |   >= v1.0    |
|        cmake        |        Cross platform build system generator        |  >= 3.16.3-3  |   >= v1.0    |
|       ccache        | Compiler cache for fast recompilation of C/C++ code |  >= 3.7.9-1   |   >= v1.0    |

### Version control systems

| Debian package name |                      Description                      |    Version    | Available in |
| :-----------------: | :---------------------------------------------------: | :-----------: | :----------: |
|         git         |  fast, scalable, distributed revision control system  | >= 1:2.26.2-1 |   >= v1.0    |
|      git-flow       | Git extension to provide a high-level branching model |  >= 1.12.3-1  |   >= v1.0    |



### Script Interpreters

| Debian package name |              Description              |  Version   | Available in |
| :-----------------: | :-----------------------------------: | :--------: | :----------: |
|       python3       | Python scripting language interpreter | >= 3.8.2-3 |   >= v1.0    |

### Package managers

| Debian package name |       Description        |  Version  | Available in |
| :-----------------: | :----------------------: | :-------: | :----------: |
|        pip3         | Python package installer | >= 20.1-2 |   >= v1.0    |
|  conan (via pip3)   |   C++ Package Manager    | >= 1.25.0 |   >= v1.0    |

### Code linter/formatter & static analyzers

| Debian package name |                 Description                 |    Version    | Available in |
| :-----------------: | :-----------------------------------------: | :-----------: | :----------: |
|   clang-format-10   |       Tool to format C/C++/Obj-C code       | >= 1:10.0.0-4 |   >= v1.0    |
|    clang-tidy-10    |         clang-based C++ linter tool         | >= 1:10.0.0-4 |   >= v1.0    |
|        iwyu         | Analyze #includes in C and C++ source files |   >= 8.0-4    |   >= v1.0    |
|      cppcheck       |  tool for static C/C++ code analysis (CLI)  |   >= 1.90-4   |   >= v1.0    |

### Tracing/diagnostics/analysis

| Debian package name |                         Description                          |    Version    | Available in |
| :-----------------: | :----------------------------------------------------------: | :-----------: | :----------: |
|      valgrind       | instrumentation framework for building dynamic analysis tools | >= 1:3.15.0-1 |   >= v1.0    |

### Unit testing/mocking/benchmarking

| Debian package name |                    Description                    |   Version   | Available in |
| :-----------------: | :-----------------------------------------------: | :---------: | :----------: |
|    libgtest-dev     |   Google's framework for writing C++ unit tests   | >= 1.10.0-3 |   >= v1.0    |
|    libgmock-dev     |   Google's framework for writing C++ mock code    | >= 1.10.0-3 |   >= v1.0    |
|  libbenchmark-dev   | Microbenchmark support library, development files | >= 1.5.0-4  |   >= v1.0    |

### Code coverage analysis

| Debian package name |                        Description                        |  Version  | Available in |
| :-----------------: | :-------------------------------------------------------: | :-------: | :----------: |
|        lcov         |       Summarise Code coverage information from GCOV       | >= 1.14-2 |   >= v1.0    |
|        gcovr        | Manages the compilation of coverage information from gcov | >= 4.2-1  |   >= v1.0    |

### Documentation

| Debian package name |                         Description                          |   Version   | Available in |
| :-----------------: | :----------------------------------------------------------: | :---------: | :----------: |
|       doxygen       | Documentation system for C, C++, Java, Python and other languages | >= 1.8.17-1 |   >= v1.0    |
|    doxygen-latex    |  Adds latex format support for doxygen document generation   | >= 1.8.17-1 |   >= v1.0    |
|  doxygen-doxyparse  |      multi-language source code parser based on Doxygen      | >= 1.8.17-1 |   >= v1.0    |
|      graphviz       |               rich set of graph drawing tools                | >= 2.42.2-4 |   >= v1.0    |

### Misc

| Debian package name |                  Description                  |    Version    | Available in |
| :-----------------: | :-------------------------------------------: | :-----------: | :----------: |
|      iproute2       |     networking and traffic control tools      |  >= 5.6.0-1   |   >= v1.0    |
|       procps        |          /proc file system utilities          | >= 2:3.3.16-4 |   >= v1.0    |
|     lsb-release     | Linux Standard Base version reporting utility |   >= 11.1.0   |   >= v1.0    |



## License

This project is licensed under MIT license. See LICENSE file for details.