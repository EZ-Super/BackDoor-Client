cmake_minimum_required(VERSION 3.25)
project(Marauder)

set(CMAKE_CXX_STANDARD 98)

# 指定使用 Windows 编译环境
set(CMAKE_SYSTEM_NAME Windows)
set(CMAKE_C_COMPILER x86_64-w64-mingw32-gcc)
set(CMAKE_CXX_COMPILER x86_64-w64-mingw32-g++)

# 生成的可执行文件
add_executable(Marauder src/main.cpp)

# 链接 Windows 所需的库
target_link_libraries(Marauder kernel32 user32 gdi32)
target_link_libraries(Marauder ws2_32)

# 静态链接以避免依赖 DLL
set(CMAKE_EXE_LINKER_FLAGS "-static-libgcc -static-libstdc++")
