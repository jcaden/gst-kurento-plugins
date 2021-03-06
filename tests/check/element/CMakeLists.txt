set (SUPRESSIONS "${CMAKE_CURRENT_SOURCE_DIR}/../valgrind.supp")

add_test_program (test_httpendpoint httpendpoint.c)
add_dependencies(test_httpendpoint kmscore)
target_include_directories(test_httpendpoint PRIVATE
                           ${KMSGSTCOMMONS_INCLUDE_DIRS}
                           ${GSTREAMER_INCLUDE_DIRS}
                           ${GSTREAMER_CHECK_INCLUDE_DIRS}
                           "${CMAKE_CURRENT_SOURCE_DIR}/../../../src/gst-plugins")

target_link_libraries(test_httpendpoint
                      ${GSTREAMER_LIBRARIES}
                      ${GSTREAMER_CHECK_LIBRARIES}
                      ${KMSGSTCOMMONS_LIBRARIES})

add_test_program (test_recorderendpoint recorderendpoint.c)
add_dependencies(test_recorderendpoint kmscore)
target_include_directories(test_recorderendpoint PRIVATE
                           ${KMSGSTCOMMONS_INCLUDE_DIRS}
                           ${GSTREAMER_INCLUDE_DIRS}
                           ${GSTREAMER_CHECK_INCLUDE_DIRS}
                           "${CMAKE_CURRENT_SOURCE_DIR}/../../../src/gst-plugins")
target_link_libraries(test_recorderendpoint
                      ${GSTREAMER_LIBRARIES}
                      ${GSTREAMER_CHECK_LIBRARIES}
                      ${KMSGSTCOMMONS_LIBRARIES})

add_test_program (test_playerendpoint playerendpoint.c)
add_dependencies(test_playerendpoint kmstestutils kmscore)
target_include_directories(test_playerendpoint PRIVATE
                           ${KMSGSTCOMMONS_INCLUDE_DIRS}
                           ${GSTREAMER_INCLUDE_DIRS}
                           ${GSTREAMER_CHECK_INCLUDE_DIRS}
                           "${CMAKE_CURRENT_SOURCE_DIR}/../../../src/gst-plugins")
target_link_libraries(test_playerendpoint
                      ${GSTREAMER_LIBRARIES}
                      ${GSTREAMER_CHECK_LIBRARIES}
                      ${KMSGSTCOMMONS_LIBRARIES}
                      kmstestutils)

add_test_program (test_rtpendpoint rtpendpoint.c)
add_dependencies(test_rtpendpoint kmstestutils kmscore)
target_include_directories(test_rtpendpoint PRIVATE
                           ${KMSGSTCOMMONS_INCLUDE_DIRS}
                           ${GSTREAMER_INCLUDE_DIRS}
                           ${GSTREAMER_CHECK_INCLUDE_DIRS})
target_link_libraries(test_rtpendpoint
                      ${GSTREAMER_LIBRARIES}
                      ${GSTREAMER_CHECK_LIBRARIES}
                      ${KMSGSTCOMMONS_LIBRARIES}
                      kmstestutils)

add_test_program (test_rtpendpoint_audio rtpendpoint_audio.c)
add_dependencies(test_rtpendpoint_audio kmstestutils kmscore)
target_include_directories(test_rtpendpoint_audio PRIVATE
                           ${KMSGSTCOMMONS_INCLUDE_DIRS}
                           ${GSTREAMER_INCLUDE_DIRS}
                           ${GSTREAMER_CHECK_INCLUDE_DIRS})
target_link_libraries(test_rtpendpoint_audio
                      ${GSTREAMER_LIBRARIES}
                      ${GSTREAMER_CHECK_LIBRARIES}
                      ${KMSGSTCOMMONS_LIBRARIES}
                      kmstestutils)

add_test_program (test_rtpendpoint_video rtpendpoint_video.c)
add_dependencies(test_rtpendpoint_video kmstestutils kmscore)
target_include_directories(test_rtpendpoint_video PRIVATE
                           ${KMSGSTCOMMONS_INCLUDE_DIRS}
                           ${GSTREAMER_INCLUDE_DIRS}
                           ${GSTREAMER_CHECK_INCLUDE_DIRS})
target_link_libraries(test_rtpendpoint_video
                      ${GSTREAMER_LIBRARIES}
                      ${GSTREAMER_CHECK_LIBRARIES}
                      ${KMSGSTCOMMONS_LIBRARIES}
                      kmstestutils)

# add_test_program (test_webrtcendpoint webrtcendpoint.c)
# add_dependencies(test_webrtcendpoint kmstestutils kmsplugin)
# target_include_directories(test_webrtcendpoint PRIVATE
#                            ${KMSGSTCOMMONS_INCLUDE_DIRS}
#                            ${GSTREAMER_INCLUDE_DIRS}
#                            ${GSTREAMER_CHECK_INCLUDE_DIRS})
# target_link_libraries(test_webrtcendpoint
#                       ${GSTREAMER_LIBRARIES}
#                       ${GSTREAMER_CHECK_LIBRARIES}
#                       ${KMSGSTCOMMONS_LIBRARIES}
#                       kmstestutils)