cmake_minimum_required(VERSION 3.22)
project(CMSC701_A0)

set(CMAKE_CXX_STANDARD 17)


set(Boost_USE_STATIC_LIBS OFF)
set(Boost_USE_MULTITHREADED ON)
set(Boost_USE_STATIC_RUNTIME OFF)
find_package(Boost REQUIRED COMPONENTS program_options)

include_directories(${Boost_INCLUDE_DIRS}, include)

add_executable(buildsa src/buildsa.cpp
        src/sa_index.cpp
        src/sa_index.h
        src/fasta_reader.cpp
        src/fasta_reader.h
        src/genome.cpp
        src/genome.h
)
target_link_libraries(buildsa ${Boost_LIBRARIES})

add_executable(inspectsa src/inspectsa.cpp
        src/sa_index.cpp
        src/sa_index.h
        src/fasta_reader.cpp
        src/fasta_reader.h
        src/genome.cpp
        src/genome.h
)
target_link_libraries(inspectsa ${Boost_LIBRARIES})
add_executable(querysa src/querysa.cpp
        src/query.cpp
        src/query.h
        src/sa_index.cpp
        src/sa_index.h
        src/fasta_reader.cpp
        src/fasta_reader.h
        src/genome.cpp
        src/genome.h
)
target_link_libraries(querysa ${Boost_LIBRARIES})
