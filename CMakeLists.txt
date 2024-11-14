cmake_minimum_required(VERSION 3.29)
project(Final_project_game)

set(CMAKE_CXX_STANDARD 20)

set(SDL2_PATH "SDL_lib/SDL2-2.30.7/x86_64-w64-mingw32")
set(SDL2_IMAGE_PATH "SDL_lib/SDL2_image-2.8.2/x86_64-w64-mingw32")
set(SDL2_TTF_PATH "SDL_lib/SDL2_ttf-2.22.0/x86_64-w64-mingw32")

list(APPEND CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/cmake_modules")
find_package(SDL2 REQUIRED)
find_package(SDL2_image REQUIRED)
find_package(SDL2_ttf REQUIRED)

include_directories(${SDL2_INCLUDE_DIR} ${SDL2_IMAGE_PATH}/include ${SDL2_TTF_PATH}/include )
#link_directories(${SDL2_IMAGE_PATH}/lib/x64)

add_executable(Final_project_game main.cpp
        src/graphics.h
        src/SDL_bgi.cpp
        src/SDL_bgi.h
)

target_link_libraries(${PROJECT_NAME} ${SDL2_LIBRARY} ${SDL2_IMAGE_LIBRARIES} ${SDL2_TTF_LIBRARIES})



