set(LIB_NAME ziplib_bzip2)

project(${LIB_NAME})

set(SOURCES
        blocksort.c
        bzerror.c
        bzlib.c
        compress.c
        crctable.c
        decompress.c
        huffman.c
        randtable.c
        )

add_library(${LIB_NAME} STATIC ${SOURCES})

install(TARGETS ${LIB_NAME}
        LIBRARY DESTINATION lib)