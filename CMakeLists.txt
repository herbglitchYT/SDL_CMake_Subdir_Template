cmake_minimum_required(VERSION 3.10)

project(template)

add_executable(${PROJECT_NAME}
    src/main.cpp
)

add_subdirectory(lib/sdl)

target_include_directories(${PROJECT_NAME}
    PUBLIC lib/sdl/include
)

target_link_directories(${PROJECT_NAME}
    PUBLIC lib/sdl
)

if(WIN32 AND NOT MSVC)
    target_link_libraries(${PROJECT_NAME} mingw32 SDL2main SDL2)
else()
    target_link_libraries(${PROJECT_NAME} SDL2main SDL2)
endif()