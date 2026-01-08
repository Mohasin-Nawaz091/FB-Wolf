cmake_minimum_required(VERSION 3.8)

project(CMakeProject1)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# ================= IMGUI =================
include_directories(
    imgui
    imgui/backends
)

set(IMGUI_SRC
    imgui/imgui.cpp
    imgui/imgui_draw.cpp
    imgui/imgui_tables.cpp
    imgui/imgui_widgets.cpp
    imgui/imgui_demo.cpp
    imgui/backends/imgui_impl_win32.cpp
    imgui/backends/imgui_impl_dx11.cpp
)


# ================= EXECUTABLE =================
add_executable(CMakeProject1
    src/main.cpp
    ${IMGUI_SRC}
)

# ================= DIRECTX =================
target_link_libraries(CMakeProject1
    d3d11
    dxgi
    d3dcompiler
)
