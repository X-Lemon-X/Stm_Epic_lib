<p align="center">
  <img src="https://stmepic.nihilia.xyz/stmepic-high-resolution-logo-transparent.webp" alt="StmEpic Logo" width="40%"/>
</p>

## StmEpic library

<p align="center">
  <img src="https://github.com/X-Lemon-X/StmEpic/actions/workflows/formater.yml/badge.svg?branch=main" alt="formater"/>
  <img src="https://github.com/X-Lemon-X/StmEpic/actions/workflows/build_gnu_arm13.yml/badge.svg?branch=main" alt="gnu13"/>
  <img src="https://github.com/X-Lemon-X/StmEpic/actions/workflows/build_gnu_arm12.yml/badge.svg?branch=main" alt="gnu12"/>
  <img src="https://github.com/X-Lemon-X/StmEpic/actions/workflows/build_gnu_arm11.yml/badge.svg?branch=main" alt="gnu11"/>
</p>

This library is a collection of algoritms and interfaces to be used in robotics projects with FreeRtos as operating system. The library is designed to be used with the STM32 series of microcontrollers.
The library provides a set of classes that can be used to quickly combine bunch of sensors, engines, servos, and comunication protocols, in a meaningful way that they can work with each other out of the box, with litle to none configuration.
The library is written in C++ and is designed to be used with the code generation tool STM32CubeMX for super quick startup and changes.

## Features

- **FreeRTOS** embeded FreeRTOS as task scheduler.
- **ETL** Included **Embedded Template Library** library for containers and so on [link](https://github.com/ETLCPP/etl).
- **CanControler**: Read and write data from the CAN bus, with easy to use callbacks.
- **Device**: Interface to handle device status, reset or connection, Allow to handle devices like ICs to other Boards or drivers.
- **Dfu**: Class that can be used to enable the USB as programing using DFU [hardware support required].
- **Encoders**: Interface to read data from different types of encoders.
- **Filters**: Set of filters that can be used to filter data.
- **Gpio**: Wraper for the GPIO pins on the microcontroller.
- **Hash**: Hashing algoritms.
- **Logger**: Log data to the console via USB in json format with usefull fields like current time or software version and so on (debug,info,warning,and error).
- **Memory**: Set of classes that can be used to read and write data to FRAM or FLASH memory.
- **Motors**: Interface that can be used to control different type of engines STEPERS, BLDC, DC motors. With the same control algoritms and interfaces.
- **Movement**: Interface that can be used to control different type of engines STEPERS, BLDC, dc and so on. Using the same control algoritms and interfaces.
- **Sensors**: Set of classes that can be used to read data from different sensors.
- **Status** Return types for proper error return types from functions.
- **Timing**: Interface to add task that run at very specifi fequency (it's not a replacement for RTOS, it's simple if stemnt replacement with proper time handling).

## How to add the library to your project

1. Clone the repository to your project directory **DON'T FORGET TO INITIALIZE SUBMODULES**.
2. Add the following line to your CMakeLists.txt file:

```cmake
set(FREERTOS_PORT GCC_ARM_CM4F CACHE STRING "") # set appropriate port for your microcontroller
set(FREERTOS_HEAP 4 CACHE STRING "") # set appropriate heap implementation
set(FREERTOS_CONFIG_FILE_DIRECTORY "${CMAKE_CURRENT_SOURCE_DIR}/src") # set appropriate path to FreeRTOSConfig.h config file
add_subdirectory(StmEpic)
target_link_libraries( <YOUR_PROEJCT_NAME> PUBLIC  stmepic)
```

3. Now you can simply include header files.

## How to use the library

The library is designed to be used with the code generation tool STM32CubeMX.

1. Create a new project in STM32CubeMX.
2. In the project settings, set generate code as CMakelist.
3. Include all source files from the library to the project.
4. don't forget to have ARM GCC toolchain installed. You can download it from [here](https://developer.arm.com/tools-and-software/open-source-software/developer-tools/gnu-toolchain/gnu-rm) or get docker image to build the project from [here](https://hub.docker.com/repository/docker/xlemonx/arm-gnu-toolchain).

## Documentation

You can find StmEpic documentation on our [website](https://stmepic.nihilia.xyz).
