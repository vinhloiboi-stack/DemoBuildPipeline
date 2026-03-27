cmake -S . -B build
cmake --build build -j
cd build
ctest
