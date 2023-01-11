set(LIB_NAME ziplib)

project(${LIB_NAME})

set(SOURCES
        ZipArchive.cpp
        ZipArchiveEntry.cpp
        ZipFile.cpp
        detail/EndOfCentralDirectoryBlock.cpp
        detail/ZipCentralDirectoryFileHeader.cpp
        detail/ZipGenericExtraField.cpp
        detail/ZipLocalFileHeader.cpp
        )

set(INSTALL_HEADERS
        ZipArchive.h
        ZipArchiveEntry.h
        ZipFile.h
        detail/EndOfCentralDirectoryBlock.h
        detail/ZipCentralDirectoryFileHeader.h
        detail/ZipGenericExtraField.h
        detail/ZipLocalFileHeader.h)

add_library(${LIB_NAME} STATIC ${SOURCES})

target_link_libraries(${LIB_NAME}
        PRIVATE ziplib_bzip2 ziplib_lzma ziplib_zlib
        )

target_sources(${LIB_NAME}
        PUBLIC FILE_SET HEADERS
        BASE_DIRS ${CMAKE_CURRENT_SOURCE_DIR}
        FILES "${INSTALL_HEADERS}")

install(TARGETS ${LIB_NAME}
        LIBRARY DESTINATION lib
        FILE_SET HEADERS)