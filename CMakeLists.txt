cmake_minimum_required(VERSION 3.5)
project(d3d11_hook)
set(CMAKE_PREFIX_PATH ${CMAKE_CURRENT_LIST_DIR}/minhook_debug_x64/lib/minhook) #…Ë÷√minhook¬∑æ∂

find_package(minhook)
include_directories(${CMAKE_CURRENT_LIST_DIR}/imgui_d11)
add_library(${PROJECT_NAME} SHARED dll_main.cpp 
${CMAKE_CURRENT_LIST_DIR}/imgui_d11/imgui.cpp 
${CMAKE_CURRENT_LIST_DIR}/imgui_d11/imgui_impl_dx11.cpp 
${CMAKE_CURRENT_LIST_DIR}/imgui_d11/imgui_impl_win32.cpp
${CMAKE_CURRENT_LIST_DIR}/imgui_d11/imgui_draw.cpp
${CMAKE_CURRENT_LIST_DIR}/imgui_d11/imgui_tables.cpp
${CMAKE_CURRENT_LIST_DIR}/imgui_d11/imgui_widgets.cpp)
target_link_libraries(${PROJECT_NAME} d3d11.lib minhook::minhook)