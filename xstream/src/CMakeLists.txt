list(APPEND EXTRA_INCLUDE_DIRS ${CMAKE_SOURCE_DIR}/src)

add_library(xstream base64.cpp
                    bz.cpp 
                    common.cpp 
                    dater.cpp 
                    debug.cpp 
                    digest.cpp
                    fd.cpp
                    md5.cpp
                    posix.cpp
                    tee.cpp
                    xdr.cpp
                    z.cpp
                    z_digest.cpp
           )
set_property(TARGET xstream PROPERTY POSITION_INDEPENDENT_CODE ON)

# add to the include list
target_include_directories(xstream PUBLIC
                           ${BZIP2_INCLUDE_DIRS}
                           ${ZLIB_INCLDUE_DIRS}
                           ${EXTRA_INCLUDE_DIRS}
                           ${CMAKE_CURRENT_SOURCE_DIR}/../include
                          )

