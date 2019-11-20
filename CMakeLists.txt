# CMakeList.txt : 最上位の CMake プロジェクト ファイル。グローバル構成を行います
# また、サブプロジェクトをここに含めます。
#
cmake_minimum_required (VERSION 3.8)

PROJECT("RealWorldDigitize" CXX)

add_library(rwdigitize rwdigitize.cpp)
install(TARGETS rwdigitize DESTINATION lib/${CMAKE_LIBRARY_ARCHITECTURE})
install(FILES rwdigitize.hpp DESTINATION include/${CMAKE_LIBRARY_ARCHITECTURE})

# サブプロジェクトを含めます。

add_executable(rwd_test test.cpp)
target_link_libraries(rwd_test rwdigitize)
