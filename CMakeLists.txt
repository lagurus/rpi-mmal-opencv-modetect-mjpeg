cmake_minimum_required(VERSION 2.8)

SET(COMPILE_DEFINITIONS -Werror)

include_directories(/opt/vc/include)
include_directories(/opt/vc/include/interface/vcos/pthreads)
include_directories(/opt/vc/include/interface/vmcs_host)
include_directories(/opt/vc/include/interface/vmcs_host/linux)

#include_directories(/home/pi/src/raspberrypi/userland)
#include_directories(/opt/vc/src/hello_pi/libs/vgfont)

link_directories(/opt/vc/lib)

#FIND_LIBRARY(RASPI_LIB /opt/vc/lib/)
#set(CMAKE_LIBRARY_PATH ${CMAKE_LIBRARY_PATH} /opt/vc/lib)
#LINK_DIRECTORIES(/opt/vc/lib)


add_executable(mmal_mjpeg_test mmal_mjpeg.c)

#target_link_libraries(mmal_opencv_modect mmal_core mmal_util mmal_vc_client vcos bcm_host openmaxil EGL pthread rt)
target_link_libraries(mmal_mjpeg_test mmal_core mmal_util mmal_vc_client vcos bcm_host openmaxil brcmEGL pthread rt)

