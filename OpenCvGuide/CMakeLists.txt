cmake_minimum_required(VERSION 3.10)
set(TARGET_NAME OpenCvGuide)
project(${TARGET_NAME} VERSION 0.1 LANGUAGES CXX)

# Find OpenCV
find_package(OpenCV)
if(OpenCV_FOUND)
	include_directories(${OpenCV_INCLUDE_DIRS})
endif()

add_executable(${TARGET_NAME} GuideOpencvV1.cpp GuideOpencvV1.h)
target_link_libraries(${TARGET_NAME} PUBLIC ${OpenCV_LIBS})

#set_target_properties(${TARGET_NAME} PROPERTIES FOLDER Demo)

set_property(TARGET ${TARGET_NAME}  PROPERTY CXX_STANDARD 17)
target_include_directories(${TARGET_NAME} PRIVATE ${CMAKE_SOURCE_DIR})
target_compile_definitions(${TARGET_NAME} PUBLIC -D_UNICODE -DUNICODE -DNOMINMAX)