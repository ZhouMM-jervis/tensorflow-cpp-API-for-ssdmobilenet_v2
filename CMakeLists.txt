cmake_minimum_required(VERSION 3.3 FATAL_ERROR)
add_executable(example example.cpp)

# try the shared tensorflow library first
find_package(TensorflowCC COMPONENTS Shared)
if(TensorflowCC_Shared_FOUND)
  target_link_libraries(example TensorflowCC::Shared)
# fallback to the static library
else()
  find_package(TensorflowCC REQUIRED COMPONENTS Static)
  target_link_libraries(example TensorflowCC::Static)
endif()

# link cuda if it is available
find_package(CUDA)
if(CUDA_FOUND)
  target_link_libraries(example ${CUDA_LIBRARIES})
endif()

#link_Opencv
FIND_PACKAGE( OpenCV REQUIRED )
TARGET_LINK_LIBRARIES(example ${OpenCV_LIBS})
MESSAGE(STATUS "OpenCV_LIBS: ${OpenCV_LIBS}")
