add_definitions("-DACSDK_LOG_MODULE=speakerManager")

add_library(SpeakerManager SpeakerManager.cpp
                                  ChannelVolumeManager.cpp
                                  DefaultChannelVolumeFactory.cpp
                                  SpeakerManagerComponent.cpp
                                  SpeakerManagerMiscStorage.cpp
                                  SpeakerManagerConfigHelper.cpp)

target_include_directories(SpeakerManager PUBLIC
        "${ContextManager_INCLUDE_DIRS}"
        "${SpeakerManager_SOURCE_DIR}/include")

target_link_libraries(SpeakerManager AVSCommon acsdkManufactory acsdkShutdownManagerInterfaces Endpoints)

# install target
asdk_install()
