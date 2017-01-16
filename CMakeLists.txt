cmake_minimum_required(VERSION 2.6)
project(soil)

find_package(OpenGL REQUIRED)
find_package(GLEW REQUIRED)

ADD_LIBRARY(${PROJECT_NAME} STATIC
        src/image_helper.c
        src/stb_image_aug.c
        src/image_DXT.c
        src/SOIL.c)
target_include_directories(${PROJECT_NAME}
        PUBLIC inc
        PRIVATE ${OPENGL_INCLUDE_DIR} ${GLEW_INCLUDE_DIRS})
target_link_libraries(${PROJECT_NAME} ${OPENGL_gl_LIBRARY} ${GLEW_LIBRARIES})
