cmake_minimum_required(VERSION 3.1)
project(trt_image_classification)

set(CMAKE_BUILD_TYPE DEBUG)

find_package(OpenCV REQUIRED)
find_package(CUDA REQUIRED)

# tensorrt dir 
set(TRT_ROOT /home/darknet/CM/profile/TensorRT-7.2.2.3/)
set(TRT_PLUGIN /home/darknet/CM/12_tensorrt/TensorRT/libs)

include_directories(${CMAKE_SOURCE_DIR}
                    ${CMAKE_SOURCE_DIR}/../../common/
                    ${TRT_ROOT}/include)

link_directories(${TRT_PLUGIN})
# link_directories(${TRT_ROOT}/lib)

set(CUDA_NVCC_FLAGS --std=c++11)
set(CMAKE_CXX_STANDARD 11)

cuda_add_executable(classify_image classification.cpp)
target_link_libraries(classify_image nvinfer_plugin nvinfer ${OpenCV_LIBS})