set(LIB_NAME ziplib_lzma)

project(${LIB_NAME})

set(SOURCES
        7zAlloc.c
        7zBuf.c
        7zBuf2.c
        7zCrc.c
        7zCrcOpt.c
        7zDec.c
        7zFile.c
        7zIn.c
        7zStream.c
        Alloc.c
        Bcj2.c
        Bra.c
        Bra86.c
        BraIA64.c
        CpuArch.c
        Delta.c
        LzFind.c
        LzFindMt.c
        Lzma2Dec.c
        Lzma2Enc.c
        Lzma86Dec.c
        Lzma86Enc.c
        LzmaDec.c
        LzmaEnc.c
        LzmaLib.c
        MtCoder.c
        Ppmd7.c
        Ppmd7Dec.c
        Ppmd7Enc.c
        Sha256.c
        Threads.c
        Xz.c
        XzCrc64.c
        XzDec.c
        XzEnc.c
        XzIn.c
        )

add_library(${LIB_NAME} STATIC ${SOURCES})

install(TARGETS ${LIB_NAME}
        LIBRARY DESTINATION lib)