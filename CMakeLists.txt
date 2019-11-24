cmake_minimum_required(VERSION 2.8.0)
project(svm_classifier)

set(CMAKE_CXX_FLAGS -std=c++11)
set(EXECUTABLE_OUTPUT_PATH ../bin)     # 设置生成的可执行文件的路径
set(LIBRARY_OUTPUT_PATH ../lib)        # 设置生成的库的路径
set(CMAKE_BUILD_TYPE Debug)            # 设置编译的类型Debug/Release

set(THIRDPARTY_DIR /home/geoff/workspace/third_party)

include_directories(                   # 设置头文件目录
	${THIRDPARTY_DIR}/grt/include
)

link_directories(                      # 设置库目录
	${THIRDPARTY_DIR}/grt/lib
)

set(GRT_LIBS grt)

add_executable(classifier src/SVMExample.cpp)
target_link_libraries(classifier ${GRT_LIBS})

#add_library(classifier SHARED src/SVMExample.cpp)  # SHARED 设置生成动态库， 不加生成静态库
#target_link_libraries(classifier ${GRT_LIBS})
