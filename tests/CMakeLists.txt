cmake_minimum_required (VERSION 3.8)

#include_directories( ${CMAKE_CURRENT_SOURCE_DIR}/cli ${CMAKE_CURRENT_SOURCE_DIR}/lib ${CMAKE_CURRENT_SOURCE_DIR}/package1 ${CMAKE_CURRENT_SOURCE_DIR}/package2) 

project (runUnitTests) 

# tests
enable_testing()

include_directories(/usr/src/gtest/include /usr/src/gtest)

################################
# Unit Tests
################################

# Add test cpp file
add_executable( test_component1 unittests/test_component1.cc "../src/component1.cc")
# Link test executable against gtest & gtest_main
target_link_libraries(test_component1 gtest gtest_main pthread)
add_test( NAME unitTestsComponent1 COMMAND test_component1 --gtest_output=xml:${CMAKE_BINARY_DIR}/test_component1-report.xml )

add_executable( test_fname_in_both unittests/test_fname_in_both.cc )
# Link test executable against gtest & gtest_main
target_link_libraries(test_fname_in_both gtest gtest_main pthread)
add_test( NAME unitTestsFnameInBoth COMMAND test_fname_in_both --gtest_output=xml:${CMAKE_BINARY_DIR}/test_fname_in_both-report.xml )

# Add test cpp file
add_executable( test_fname_in_tc unittests/test_fname_in_tc.cc )
# Link test executable against gtest & gtest_main
target_link_libraries(test_fname_in_tc gtest gtest_main pthread)
add_test( NAME unitTestsFnameInTc COMMAND test_fname_in_tc --gtest_output=xml:${CMAKE_BINARY_DIR}/test_fname_in_tc-report.xml )

# Add test cpp file
add_executable( test_fname_in_ts unittests/test_fname_in_ts.cc )
# Link test executable against gtest & gtest_main
target_link_libraries(test_fname_in_ts gtest gtest_main pthread)
add_test( NAME unitTestsFnameInTs COMMAND test_fname_in_ts --gtest_output=xml:${CMAKE_BINARY_DIR}/test_fname_in_ts-report.xml )

# Add test cpp file
add_executable( test_two_fixtures unittests/test_two_fixtures.cc )
# Link test executable against gtest & gtest_main
target_link_libraries(test_two_fixtures gtest gtest_main pthread)
add_test( NAME unitTestsTwoFixtures COMMAND test_two_fixtures --gtest_output=xml:${CMAKE_BINARY_DIR}/test_two_fixtures-report.xml )

# Add test cpp file
add_executable( test_without_fixture unittests/test_without_fixture.cc )
# Link test executable against gtest & gtest_main
target_link_libraries(test_without_fixture gtest gtest_main pthread)
add_test( NAME unitTestsWithoutFixture COMMAND test_without_fixture --gtest_output=xml:${CMAKE_BINARY_DIR}/test_without_fixture-report.xml )
