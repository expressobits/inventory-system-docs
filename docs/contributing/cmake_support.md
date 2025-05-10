# CMake support

### git submodule setup in main repository
`git submodule init`  
`git submodule update`

### cmake configure in main repository
`cmake -GNinja -DCMAKE_BUILD_TYPE=Debug -B cmake-build-debug .`

Define variables GODOTCPP_PRECISION=single|double and/or BITS=32|64 for further build variants if needed.

### cmake build/install in specified build folder cmake-build-debug
`cmake --build . --target install --config Debug`

This installs the built library in the bin folder of the repository.