# benchmarking library
file(GLOB BENCHMARK_FILES "benchmarking.c" "benchmarking_sec.c")
add_library(BENCHMARK_LIB STATIC ${BENCHMARK_FILES})

# benchmarking tests
file(GLOB BENCHMARK_TEST_FILES "benchmarking_naive.c")
add_executable(benchmark_naive ${BENCHMARK_TEST_FILES})
target_link_libraries(benchmark_naive PRIVATE multiplication_lib BENCHMARK_LIB)

# benchmarking tests
file(GLOB BENCHMARK_TEST_FILES "benchmarking_transpose.c")
add_executable(benchmark_transpose ${BENCHMARK_TEST_FILES})
target_link_libraries(benchmark_transpose PRIVATE multiplication_lib BENCHMARK_LIB)

# benchmarking tests
file(GLOB BENCHMARK_TEST_FILES "benchmarking_vectorization.c")
add_executable(benchmark_vectorization ${BENCHMARK_TEST_FILES})
target_link_libraries(benchmark_vectorization PRIVATE multiplication_lib BENCHMARK_LIB)

# benchmarking tests
file(GLOB BENCHMARK_TEST_FILES "benchmarking_asm.c")
add_executable(benchmark_asm ${BENCHMARK_TEST_FILES})
target_link_libraries(benchmark_asm PRIVATE multiplication_lib BENCHMARK_LIB)

# benchmarking tests
file(GLOB BENCHMARK_TEST_FILES "benchmarking_vectorize_x86.c")
add_executable(benchmark_vectorize_x86 ${BENCHMARK_TEST_FILES})
target_link_libraries(benchmark_vectorize_x86 PRIVATE multiplication_lib BENCHMARK_LIB)

# benchmarking tests
file(GLOB BENCHMARK_TEST_FILES "benchmarking_block_transpose.c")
add_executable(benchmark_block_transpose ${BENCHMARK_TEST_FILES})
target_link_libraries(benchmark_block_transpose PRIVATE multiplication_lib BENCHMARK_LIB)
