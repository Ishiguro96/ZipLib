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

add_library(${LIB_NAME} STATIC ${SOURCES})

target_link_libraries(${LIB_NAME}
        PRIVATE ziplib_bzip2 ziplib_lzma ziplib_zlib
        )

install(TARGETS ${LIB_NAME}
        LIBRARY DESTINATION lib)

install(DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}
        DESTINATION include/
        FILES_MATCHING PATTERN "*.h")