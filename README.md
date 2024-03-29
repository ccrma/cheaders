# ChucK Headers for Chugins Development
Official header file(s) for ChucK plugin (chugin) deveopment.

Related source repositories
* [chuck](https://github.com/ccrma/chuck) : chuck core (compiler, vm, synthesis engine), used in various chuck hosts
* [chugins](https://github.com/ccrma/chugins) : chugins maintained by ChucK Team

# One header to compile them all...
As of chuck-1.5.2.0 (November 2023), all chugins require a single header file `chugin.h` for compilation. 
* chuck c++ typedefs and #defines such as t_CKINT, t_CKFLOAT, etc.
* macros for defining chugin components, e.g., member functions, contructors, operator overloads
* chugin DL query API for adding new types to the ChucK type system
* chugin DL runtime API for accessing host functionalities across shared-library boundaries
* header version string CHUCK_VERSION_STRING (associated with a particular chuck language version)
* host/chugin compatibility version (used when a chugin loads to determine chugin:host compatibility)

FYI: `chugin.h` was generated by [chuck-o-matic/scripts/chugin-gen-header.sh](https://github.com/ccrma/chuck-o-matic/blob/main/scripts/chugins-gen-header.sh).

# CMake

If you are using cmake, you can automatically download and link a release of `cheaders` directly from github.

Add the following to your `CMakeLists.txt`:

```
include(FetchContent)
FetchContent_Declare(
    cheaders
    GIT_REPOSITORY https://github.com/ccrma/cheaders.git
    GIT_TAG main # checkout at whatever tag you need
)
FetchContent_MakeAvailable(cheaders)

target_link_libraries(myproject PRIVATE cheaders)
```
