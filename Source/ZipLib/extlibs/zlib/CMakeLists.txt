set(LIB_NAME ziplib_zlib)

project(${LIB_NAME})

set(SOURCES
        adler32.c
        compress.c
        crc32.c
        deflate.c
        infback.c
        inffast.c
        inflate.c
        inftrees.c
        trees.c
        uncompr.c
        zutil.c
        )

add_library(${LIB_NAME} STATIC ${SOURCES})

install(TARGETS ${LIB_NAME}
        LIBRARY DESTINATION lib)