# CMakeLists.txt in cheaders directory

# Define the library
add_library(cheaders include/chugin.h)

set_target_properties(cheaders PROPERTIES LINKER_LANGUAGE CXX)

# Include the directory containing chugin.h
target_include_directories(cheaders PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/include)
