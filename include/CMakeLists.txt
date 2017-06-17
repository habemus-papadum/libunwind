install(DIRECTORY .
        DESTINATION include
        COMPONENT unwind-headers
        FILES_MATCHING
        PATTERN *
        PATTERN "CMakeLists.txt" EXCLUDE
        PERMISSIONS OWNER_READ OWNER_WRITE GROUP_READ WORLD_READ
        )
add_custom_target(install-unwind-headers
        COMMAND "${CMAKE_COMMAND}"
        -DCMAKE_INSTALL_COMPONENT=unwind-headers
        -P "${CMAKE_BINARY_DIR}/cmake_install.cmake")