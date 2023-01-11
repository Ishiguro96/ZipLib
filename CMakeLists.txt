cmake_minimum_required(VERSION 3.20)

project(ZipLib VERSION 1.0.0 LANGUAGES C CXX)

# Set compiler specific settings
set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_subdirectory(Source/ZipLib/extlibs/bzip2)
add_subdirectory(Source/ZipLib/extlibs/lzma)
add_subdirectory(Source/ZipLib/extlibs/zlib)
add_subdirectory(Source/ZipLib)