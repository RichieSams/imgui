project(imgui)

find_package(Vulkan REQUIRED)

set(IMGUI_SRC
   backends/imgui_impl_glfw.cpp
   backends/imgui_impl_glfw.h
   backends/imgui_impl_opengl3.cpp
   backends/imgui_impl_opengl3.h
   backends/imgui_impl_opengl3_loader.h
   imconfig.h
   imgui.h
   imstb_rectpack.h
   imstb_textedit.h
   imstb_truetype.h
   imgui.cpp
   imgui_demo.cpp
   imgui_draw.cpp
   imgui_tables.cpp
   imgui_internal.h
   imgui_widgets.cpp
)

add_library(imgui STATIC ${IMGUI_SRC})
target_include_directories(imgui PUBLIC . backends)

target_link_libraries(imgui glfw ${Vulkan_LIBRARIES})
target_include_directories(imgui PUBLIC ${Vulkan_INCLUDE_DIRS})
