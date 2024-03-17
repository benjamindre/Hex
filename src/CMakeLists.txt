project(HexApp)

add_executable(${PROJECT_NAME} HexApp.cpp)

target_link_libraries(${PROJECT_NAME}
                      PRIVATE
                      glad
                      imgui
)