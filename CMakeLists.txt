cmake_minimum_required(VERSION 2.8)

project(CI)

enable_testing()

add_library(MathLib
	src/Vector.h
	src/Vector.cpp
		)

add_executable(MathLibTest
	src/VectorTest.cpp)

target_link_libraries(MathLibTest MathLib)

install(TARGETS MathLib MathLibTest
	RUNTIME DESTINATION "bin/"
	LIBRARY DESTINATION "lib/"
	ARCHIVE DESTINATION "lib/static/"
	)

add_test(MathLibTestRun MathLibTest)

