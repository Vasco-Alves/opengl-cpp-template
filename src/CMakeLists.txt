# Add your executable and list your source files here
add_executable(${PROJECT_NAME} 
    main.cpp
    # When you add new files later, just add them here:
    # renderer.cpp
    # window.cpp
)

# Tell the compiler where to find your header files (like myheader.hpp)
# ${CMAKE_SOURCE_DIR} points to the root of your project
target_include_directories(${PROJECT_NAME} PRIVATE ${CMAKE_SOURCE_DIR}/include)

# Link the libraries to your executable
target_link_libraries(${PROJECT_NAME} PRIVATE
    glfw
    glad::glad
    glm::glm
    OpenGL::GL
)