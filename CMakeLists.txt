cmake_minimum_required(VERSION 3.20)

# LANGUAGES CXX：只启用 C++，跳过 C 编译器检查
# 工程名不能含 '='，否则会生成 cpp-api-test=framework.sln，IDE 调试/运行容易失败
project(cpp-api-test-framework LANGUAGES CXX)
set(CMAKE_CXX_STANDARD 17)  # 适用c++17
set(CMAKE_CXX_STANDARD_REQUIRED ON) # 不支持C++17就报错，禁止静默降级


add_executable(hello src/main.cpp)
target_compile_options(hello PRIVATE "$<$<CXX_COMPILER_ID:MSVC>:/utf-8>")
