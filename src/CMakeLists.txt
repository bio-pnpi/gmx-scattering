add_executable(gmx-scattering
        isotope.cpp
        scatteringfactors.cpp
        scattering-debye.cpp
        scattering-debye-sans.cpp
        scattering-debye-saxs.cpp
        scattering.cpp)

include_directories(
        ${GROMACS_INCLUDE_DIRS}
        ${CMAKE_SOURCE_DIR}/include)
add_definitions(${GROMACS_DEFINITIONS})

set_target_properties(gmx-scattering PROPERTIES
                      COMPILE_FLAGS "${GROMACS_CXX_FLAGS}")
target_link_libraries(gmx-scattering ${GROMACS_LIBRARIES})
