# Generated Cmake Pico project file

cmake_minimum_required(VERSION 3.13)

set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)

# initalize pico_sdk from installed location
# (note this can come from environment, CMake cache etc)
set(PICO_SDK_PATH "/home/andrea/pico/pico-sdk")

# Pull in Raspberry Pi Pico SDK (must be before project)
include(pico_sdk_import.cmake)

project(Rover_piPico_CPP C CXX ASM)

# Initialise the Raspberry Pi Pico SDK
pico_sdk_init()

# Add executable. Default name is the project name, version 0.1

add_executable(Rover_piPico_CPP Rover_piPico_CPP.cpp )

pico_set_program_name(Rover_piPico_CPP "Rover_piPico_CPP")
pico_set_program_version(Rover_piPico_CPP "0.1")

pico_enable_stdio_uart(Rover_piPico_CPP 1)
pico_enable_stdio_usb(Rover_piPico_CPP 1)

# Add the standard library to the build
target_link_libraries(Rover_piPico_CPP pico_stdlib)

# Add any user requested libraries
target_link_libraries(Rover_piPico_CPP
        hardware_i2c
        )

pico_add_extra_outputs(Rover_piPico_CPP)

