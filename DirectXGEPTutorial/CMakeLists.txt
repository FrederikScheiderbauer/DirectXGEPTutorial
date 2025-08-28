# CMakeList.txt : CMake project for DirectXGEPTutorial, include source and define
# project specific logic here.
#

set(Source_Files 
	src/main.cpp)
set(Include_Files
	inc/d3dx12.h 
	inc/Helpers.h)
# Add source to this project's executable.
add_executable (DirectXGEPTutorial ${Source_Files} ${Include_Files})

target_include_directories(DirectXGEPTutorial 
	PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/inc
		   "${PROJECT_SOURCE_DIR}/DirectX-Headers/include/directx")

target_link_libraries( DirectXGEPTutorial
    d3d12.lib
    dxgi.lib
    dxguid.lib
)
if (CMAKE_VERSION VERSION_GREATER 3.12)
  set_property(TARGET DirectXGEPTutorial PROPERTY CXX_STANDARD 20)
endif()

# TODO: Add tests and install targets if needed.
