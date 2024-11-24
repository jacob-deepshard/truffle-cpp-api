cmake_minimum_required(VERSION 3.10)
project(MyLibrary VERSION 1.0.0 LANGUAGES CXX)

add_library(MyLibrary src/MyLibrary.cpp)
target_include_directories(MyLibrary PUBLIC ${PROJECT_SOURCE_DIR}/include)

set_target_properties(MyLibrary PROPERTIES VERSION ${PROJECT_VERSION})

install(TARGETS MyLibrary
    LIBRARY DESTINATION lib
    ARCHIVE DESTINATION lib
    RUNTIME DESTINATION bin
)
install(DIRECTORY include/ DESTINATION include)

include(CPack)