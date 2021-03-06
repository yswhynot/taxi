cmake_minimum_required(VERSION 2.8)
project(taxi)

# set(CMAKE_CXX_STANDARD 11)
# set (CMAKE_CXX_FLAGS "--std=gnu++11 ${CMAKE_CXX_FLAGS}")
SET(CMAKE_CXX_FLAGS ${CMAKE_CXX_FLAGS} "-std=c++11 -pthread")
set(CMAKE_CXX_FLAGS_DEBUG "${CMAKE_CXX_FLAGS_DEBUG} -Wall")
set(CMAKE_CXX_FLAGS_RELEASE "${CMAKE_CXX_FLAGS_RELEASE} -Wall")

find_package (Threads)

set(SOURCE_FILES
        src/agent.h
        src/astar.cpp
        src/astar.h
        src/dot_graph.cpp
        src/dot_graph.h
        src/dynamicprogramming.cpp
        src/dynamicprogramming.h
        src/main.cpp
        src/maxqop.cpp
        src/maxqop.h
        src/monte-carlo.cpp
        src/monte-carlo.h
        src/olagent.h
        src/policy.cpp
        src/policy.h
        src/qlearning.cpp
        src/qlearning.h
        src/rlagent.cpp
        src/rlagent.h
        src/sarsa-lambda.cpp
        src/sarsa-lambda.h
        src/sarsa.cpp
        src/sarsa.h
        src/state.cpp
        src/state.h
        src/system.cpp
        src/system.h
        src/table.h
        src/taxi.cpp
        src/taxi.h
        src/tdagent.cpp
        src/tdagent.h
        src/uct.cpp
        src/uct.h
        src/utils.h src/HierarchicalFSMAgent.cpp src/HierarchicalFSMAgent.h src/ChoicePoint.h src/HierarchicalFSM.cpp src/HierarchicalFSM.h src/prettyprint.h src/MaxQ0Agent.cpp src/MaxQ0Agent.h src/HierarchicalAgent.cpp src/HierarchicalAgent.h src/MaxQQAgent.cpp src/MaxQQAgent.h src/statistic.h)

add_executable(taxi ${SOURCE_FILES})
TARGET_LINK_LIBRARIES(taxi boost_program_options ${CMAKE_THREAD_LIBS_INIT})
# TARGET_LINK_LIBRARIES(taxi boost_program_options pthread )
