cmake_minimum_required(VERSION 3.10)

project(robomaze-pilot VERSION 1.0)

# specify the C++ standard
set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED True)

find_package(cpprestsdk REQUIRED) # one external dependency
find_package(Boost REQUIRED system) # required by cpprest

# First, the library
add_library(astar SHARED src/astar.cpp)
target_include_directories(astar PUBLIC include)


# then, the executable, which depends on the library's target
add_executable(robomaze-client src/controller.cpp)
target_include_directories(robomaze-client PUBLIC include)
target_link_libraries(robomaze-client PUBLIC astar cpprestsdk::cpprest Boost::system)

# install everybody
install(TARGETS astar DESTINATION lib)
install(FILES include/astar.h DESTINATION include)
install(TARGETS robomaze-client DESTINATION bin)

