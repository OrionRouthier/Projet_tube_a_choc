cmake_minimum_required(VERSION 3.16)
project(ShockTubeSolver LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

add_executable(ShockTubeSolver
    main.cpp
    src/physics/State.cpp
    src/physics/EulerPhysics.cpp
    src/domain/Grid.cpp
    src/domain/BoundaryCondition.cpp
    src/schemes/LaxWendroffScheme.cpp
    src/schemes/MacCormackScheme.cpp
    src/schemes/RoeScheme.cpp
    src/problems/SodShockTube.cpp
    src/problems/ExactRiemannSolver.cpp
    src/core/SimulationEngine.cpp
    src/io/CsvExporter.cpp
    src/io/VtkExporter.cpp
)

target_include_directories(ShockTubeSolver PRIVATE
    ${CMAKE_CURRENT_SOURCE_DIR}/include
)

if(MSVC)
    target_compile_options(ShockTubeSolver PRIVATE /W4)
else()
    target_compile_options(ShockTubeSolver PRIVATE -Wall -Wextra -Wpedantic)
endif()
