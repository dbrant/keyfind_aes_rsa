cmake_minimum_required(VERSION 3.3)
project(aeskeyfinder)
include(ExternalProject)

if(CMAKE_BUILD_TYPE STREQUAL "Debug")
    set(ADDITIONAL_BUILD_FLAGS "-g")
elseif()
    set(ADDITIONAL_BUILD_FLAGS "-O4 -s -flto")
endif()

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -Wextra -pedantic ${ADDITIONAL_BUILD_FLAGS}")

file(GLOB_RECURSE SRC
    src/*.c
    src/*.h
)

add_executable(${PROJECT_NAME} ${SRC})
set_target_properties(${PROJECT_NAME} PROPERTIES LINKER_LANGUAGE C)
target_link_libraries(${PROJECT_NAME} )
