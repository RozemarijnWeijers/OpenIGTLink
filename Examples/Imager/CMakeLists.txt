PROJECT(Imager)

cmake_minimum_required(VERSION 2.4)
if(COMMAND cmake_policy)
  cmake_policy(SET CMP0003 NEW)
endif(COMMAND cmake_policy)

find_package(OpenIGTLink REQUIRED)
include(${OpenIGTLink_USE_FILE})

find_package(OpenCV REQUIRED)
set(VTK_DIR "/home/snr/Support/VTK-build")
find_package(VTK REQUIRED)
include(${VTK_USE_FILE})

ADD_EXECUTABLE(ImagerClient   ImagerClient.cxx)
TARGET_LINK_LIBRARIES(ImagerClient OpenIGTLink)
target_link_libraries(ImagerClient ${OpenCV_LIBS} )
target_link_libraries(ImagerClient ${VTK_LIBRARIES})

ADD_EXECUTABLE(ImagerClient2   ImagerClient2.cxx)
TARGET_LINK_LIBRARIES(ImagerClient2 OpenIGTLink)

ADD_EXECUTABLE(ImagerServer   ImagerServer.cxx)
TARGET_LINK_LIBRARIES(ImagerServer OpenIGTLink)

