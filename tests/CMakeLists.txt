include(FetchContent)

FetchContent_Declare(
    googletest
    GIT_REPOSITORY https://github.com/google/googletest.git
    GIT_TAG        release-1.11.0
)
FetchContent_MakeAvailable(googletest)
add_library(GTest::GTest INTERFACE IMPORTED)
target_link_libraries(GTest::GTest INTERFACE gtest_main)

add_executable(svg_tests svg_test.cpp)

target_link_libraries(svg_tests
PRIVATE
  GTest::GTest
  svg_lib)

add_test(svg_gtest svg_tests)