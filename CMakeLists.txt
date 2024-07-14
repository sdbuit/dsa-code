cmake_minimum_required(VERSION 3.20)
project(Test)
set(CMAKE_CXX_STANDARD 17)
include(FetchContent)
FetchContent_Declare(
  catch2
  GIT_REPOSITORY https://github.com/catchorg/Catch2.git
  GIT_TAG v3.4.0
)
FetchContent_MakeAvailable(catch2)
include_directories(${CMAKE_SOURCE_DIR}/include)
add_executable(collection_tester test/collection_tester.cpp)
target_link_libraries(collection_tester PRIVATE Catch2::Catch2WithMain)