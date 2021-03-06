cmake_minimum_required(VERSION 3.17)
project(PMI_T_3_H_Cpp)

set(CMAKE_CXX_STANDARD 20)

add_executable(1_primeNumberGenerator "tournament 1/1_PrimeNumberGenerator/main.cpp" "tournament 1/1_PrimeNumberGenerator/prime_gen.h")
add_executable(2_FiniteField "tournament 1/2_Finite_Field(Easy_version)/num.cpp" "tournament 1/2_Finite_Field(Easy_version)/num.h" "tournament 1/2_Finite_Field(Easy_version)/main.cpp")
add_executable(3_Date "tournament 1/3_Date/date.h" "tournament 1/3_Date/main.cpp")
add_executable(4_Set "tournament 1/4_Set/main.cpp" "tournament 1/4_Set/set.h")
add_executable(5_FiniteField "tournament 1/5_Finite_Field(Hard_version)/num.h" "tournament 1/5_Finite_Field(Hard_version)/num.cpp" "tournament 1/5_Finite_Field(Hard_version)/main.cpp")
add_executable(6_BufferedReader "tournament 1/6_BufferedReader/main.cpp" "tournament 1/6_BufferedReader/buffered_reader.h")

add_executable(1_pinter "tournament 2/1_SmartPointer/SmartPointer.h" "tournament 2/1_SmartPointer/main.cpp" "tournament 2/1_SmartPointer/Test_SmartPointer.h" "tournament 2/1_SmartPointer/Test.h")
add_executable(2_factory "tournament 2/2_factory/factory.h" "tournament 2/2_factory/main.cpp")
add_executable(3_fixed "tournament 2/3_FixedAllocator/fixed_allocator.h" "tournament 2/3_FixedAllocator/fixed_allocator.cpp")
add_executable(5_gamedatabase "tournament 2/5_GameDatabase/game_database.h" "tournament 2/5_GameDatabase/main.cpp")

add_executable(1_initialize_vector "tournament 3/1_initialize_vector/main.cpp" "tournament 3/1_initialize_vector/initialize_vector.h")
add_executable(2_binary "tournament 3/2_binary search/main.cpp" "tournament 3/2_binary search/find.h")
add_executable(4_convertable "tournament 3/4_is_convertable/main.cpp" "tournament 3/4_is_convertable/is_customly_convertible.h")
add_executable(3_visitor "tournament 3/3_graph_visitor/main.cpp" "tournament 3/3_graph_visitor/visitor.h")

add_executable(1_cipher "tournament 4/1_caesar_cipher/gen.cpp" "tournament 4/1_caesar_cipher/sol.cpp" "tournament 4/1_caesar_cipher/main.cpp" "tournament 4/1_caesar_cipher/caesar_encrypt.h")
add_executable(2_parallel "tournament 4/2_parallel_matrix_multiplication/main.cpp" "tournament 4/2_parallel_matrix_multiplication/matmul.h")
add_executable(3_queue "tournament 4/3_queue/main.cpp" "tournament 4/3_queue/solution.hpp")

add_executable(complex "LAB 1/Complex.h" "LAB 1/Rational.h" "LAB 1/tests.cpp")
add_executable(hashmap "LAB 2/hash_map.hpp" "LAB 2/tests.cpp")

add_executable(roguelike
        "LAB 3/Point.h"
        "LAB 3/Dragon.h"
        "LAB 3/Enemy.h"
        "LAB 3/Character.h"
        "LAB 3/GameLoop.h"
        "LAB 3/Gunsight.h"
        "LAB 3/Knight.h"
        "LAB 3/Map.h"
        "LAB 3/Medkit.h"
        "LAB 3/Princess.h"
        "LAB 3/Shooter.h"
        "LAB 3/Wall.h"
        "LAB 3/Zombie.h"
        "LAB 3/main.cpp")
# add coverage
# https://plugins.jetbrains.com/plugin/11031-c-c--coverage
if ("${CMAKE_CXX_COMPILER_ID}" STREQUAL "Clang")
    add_compile_options(-fprofile-instr-generate -fcoverage-mapping)
    add_link_options(-fprofile-instr-generate)
    #Uncomment in case of linker errors
    #link_libraries(clang_rt.profile-x86_64)
elseif ("${CMAKE_CXX_COMPILER_ID}" STREQUAL "GNU")
    add_compile_options(--coverage)
    #Uncomment in case of linker errors
    #link_libraries(gcov)
endif ()