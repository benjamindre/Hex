cmake_minimum_required(VERSION 3.27)
project(Hex LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(BUILD_SHARED_LIBS OFF)  # 构建静态库
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_BINARY_DIR}/bin)
set(LIBRARY_OUTPUT_PATH ${CMAKE_BINARY_DIR}/lib)
set(HEX_INCLUDE_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/include)
set(HEX_LIBRARY_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/lib)

# MSVC 编译需要指定 utf-8 编码
if (MSVC)
    add_compile_options("$<$<C_COMPILER_ID:MSVC>:/utf-8>")
    add_compile_options("$<$<CXX_COMPILER_ID:MSVC>:/utf-8>")
endif ()

file(COPY ${HEX_LIBRARY_DIRECTORY}/glfw3.lib DESTINATION ${LIBRARY_OUTPUT_PATH})

include_directories(${HEX_INCLUDE_DIRECTORY})
link_directories(${LIBRARY_OUTPUT_PATH})

add_subdirectory(external/glad)
add_subdirectory(external/imgui)
add_subdirectory(src)