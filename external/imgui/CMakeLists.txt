project(imgui)

set(IMGUI_SRC
    imgui/imgui.cpp
    imgui/imgui_demo.cpp
    imgui/imgui_draw.cpp
    imgui/imgui_tables.cpp
    imgui/imgui_widgets.cpp
    imgui/imgui_impl_glfw.cpp
    imgui/imgui_impl_opengl3.cpp
)

set(IMGUI_HEADERS
    imgui/imconfig.h
    imgui/imgui.h
    imgui/imgui_internal.h
    imgui/imstb_rectpack.h
    imgui/imstb_textedit.h
    imgui/imstb_truetype.h
    imgui/imgui_impl_opengl3.h
)

add_library(${PROJECT_NAME} ${IMGUI_SRC})
target_include_directories(${PROJECT_NAME} PUBLIC imgui)
target_link_libraries(${PROJECT_NAME} PRIVATE glfw3)