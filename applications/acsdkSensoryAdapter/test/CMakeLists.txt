set(INCLUDES "${SENSORY_SOURCE_DIR}/include" "${KWD_SOURCE_DIR}/include" "${SENSORY_KEY_WORD_DETECTOR_INCLUDE_DIR}")

set(INPUTFOLDER "${acsdkKWDImplementations_SOURCE_DIR}/inputs")

discover_unit_tests("${INCLUDES}" SENSORY "${INPUTFOLDER}")
