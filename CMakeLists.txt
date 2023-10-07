cmake_minimum_required(VERSION 3.8)
set(CMAKE_CXX_STANDARD 17)

project(01.hello_world)

add_executable(hello_world
        hello_world.cpp
        example.cpp
        move_me_out.cpp
        move_me_out.h
        example.h
)
target_compile_features(hello_world PUBLIC cxx_std_17)
if(MSVC)
    target_compile_options(hello_world PUBLIC /w4 /WX)
elseif(MINGW)
    target_compile_options(hello_world PUBLIC -Wall -Wextra -Werror -pedantic)
else()
    target_compile_options(hello_world PUBLIC -Wall -Wextra -Werror -pedantic)

endif()

