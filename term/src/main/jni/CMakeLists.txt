cmake_minimum_required(VERSION 3.4.1)
#批量add源文件
file(GLOB sourceFile *.h *.cpp *.c)
#日志打印
message("---------------------------------------------")
message("camke 路径：${CMAKE_SOURCE_DIR}")

add_library(
        jackpal-androidterm5      #so的名字
        SHARED          #指定是动态库
        ${sourceFile}   #参与编译打包的源文件
)


#可以省略，在下面的配置中直接写log
find_library(#find加载系统库
        log-lib
        log)
message("log库路径：${log-lib}")


message(${PROJECT_SOURCE_DIR})
#set(CMAKE_LIBRARY_OUTPUT_DIRECTORY $)


#链接库
target_link_libraries(
        jackpal-androidterm5
        ${log-lib}

)