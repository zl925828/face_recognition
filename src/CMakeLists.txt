set(BASE /home/panghao/kunlib)
add_definitions(-o3 -std=c++11)
include_directories(${BASE}/include)
link_directories(${BASE}/libs/opencv ${BASE}/libs /usr/local/lib64/)
add_library(kunFace SHARED src/faceApi.cpp)
add_executable(face_recognition  src/test.cpp)
target_link_libraries(kunFace dlib opencv_dnn  opencv_core opencv_imgproc opencv_imgcodecs)
target_link_libraries(face_recognition  kunFace dlib  opencv_dnn  opencv_core opencv_imgproc opencv_imgcodecs)
