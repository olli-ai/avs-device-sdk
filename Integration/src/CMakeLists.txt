if(BUILD_TESTING)
    add_definitions("-DACSDK_LOG_MODULE=integration")
    file(GLOB_RECURSE INTEGRATION_SRC "*.cpp")
    add_library(Integration STATIC "${INTEGRATION_SRC}")
    target_include_directories(Integration PUBLIC "${ACL_SOURCE_DIR}/include")
    target_include_directories(Integration PUBLIC "${CBLAuthDelegate_SOURCE_DIR}/include")
    target_include_directories(Integration PUBLIC "${ContextManager_SOURCE_DIR}/include")
    target_include_directories(Integration PUBLIC "${Integration_SOURCE_DIR}/include")
    target_include_directories(Integration PUBLIC "${CapabilityAgents_SOURCE_DIR}/include")
    target_include_directories(Integration PUBLIC "${AIP_SOURCE_DIR}/include")
    target_include_directories(Integration PUBLIC "${SpeechSynthesizer_SOURCE_DIR}/include")
    target_include_directories(Integration PUBLIC "${AudioPlayer_SOURCE_DIR}/include")
    target_include_directories(Integration PUBLIC "${AVSSystem_SOURCE_DIR}/include")
    target_include_directories(Integration PUBLIC "${RegistrationManager_SOURCE_DIR}/include")
    target_include_directories(Integration PUBLIC "${SQLiteStorage_SOURCE_DIR}/include")
    target_include_directories(Integration PUBLIC "${SynchronizeStateSender_SOURCE_DIR}/include")

    target_link_libraries(Integration
            ACL
            AudioResources
            CBLAuthDelegate
            ContextManager
            gtest
            gmock
            RegistrationManager
            SynchronizeStateSender
            acsdkAlerts)
    if(ACS_UTILS)
        target_link_libraries(Integration acsdkFFSAuthDelegate)
    endif()
endif()