cmake_minimum_required(VERSION 3.16)
project(LUFSMeter)

add_library(LUFSMeter STATIC
    Ebu128LoudnessMeter.h
    Ebu128LoudnessMeter.cpp
    DebugMacros.h
    filters/SecondOrderIIRFilter.cpp
    filters/SecondOrderIIRFilter.h
)

# Include directories
target_include_directories(LUFSMeter
    PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}
    PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/filters
)

target_link_libraries(LUFSMeter
    PUBLIC juce::juce_core
    PUBLIC juce::juce_audio_basics
)
