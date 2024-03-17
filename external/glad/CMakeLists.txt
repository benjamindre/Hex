project(glad)

set(GLAD_SRC glad/glad.c)
set(GLAD_HEADERS glad/glad/glad.h glad/KHR/khrplatform.h)

add_library(${PROJECT_NAME} ${GLAD_SRC})
target_include_directories(${PROJECT_NAME} PUBLIC glad)