# Embedded Internet Radio System

An end-to-end Embedded Linux project built on the BeagleBone Black.

The goal is to develop a standalone desktop internet radio while learning and applying the complete Embedded Linux software stack — from the boot process and custom Linux image to hardware integration, networking, multithreaded C++ software, and system reliability.

## Project Goals

* Understand and control the BBB boot flow: RBL → SPL → U-Boot → Linux Kernel → RootFS
* Build a custom Embedded Linux image using Buildroot
* Develop the main application in Modern C++
* Cross-compile software for the BeagleBone Black
* Stream real internet radio stations over Ethernet
* Use TCP/IP, DNS, HTTP and Linux sockets
* Implement a multithreaded streaming pipeline with a ring buffer
* Integrate physical buttons, an I2C LCD and a DS3231 RTC
* Use Device Tree and existing Linux kernel drivers where appropriate
* Add configuration files, logging and automatic startup
* Handle network failures, unavailable stations and application crashes
* Add watchdog and recovery mechanisms

## Planned System

```text
Internet Radio Station
        |
        | Ethernet / TCP / HTTP
        v
+-------------------------------+
|       BeagleBone Black        |
|                               |
|  Linux + Buildroot            |
|                               |
|  Network Thread               |
|        |                      |
|        v                      |
|    Ring Buffer                |
|        |                      |
|        v                      |
|  Playback Thread              |
|                               |
|  LCD + Buttons + RTC          |
+-------------------------------+
        |
        v
    Audio Output
```

## Hardware

* BeagleBone Black
* microSD card
* USB-to-TTL serial adapter
* LCD1602 with I2C backpack
* DS3231 RTC
* Push buttons
* Breadboard and jumper wires
* Ethernet connection

Additional audio hardware will be selected later when local playback is implemented.

## Development Environment

* Ubuntu running in VirtualBox
* Visual Studio Code
* C++
* CMake
* Git / GitHub
* GCC
* ARM cross-compilation toolchain later in the project

## Project Status

**Current milestone: Milestone 0 — Project Foundation**

Completed:

* Created the GitHub repository
* Created the local Git repository on Ubuntu
* Connected the local repository to GitHub
* Configured the main Git branch
* Installed Git and CMake
* Verified the native C++ development tools

Next:

* Create the initial CMake-based C++ project
* Verify native compilation on Ubuntu
* Commit and push the initial project structure

## Roadmap

1. Project Foundation
2. Boot Chain Ownership
3. Full Linux Boot from microSD
4. U-Boot Control
5. Custom Linux Kernel
6. Device Tree and RTC Integration
7. Minimal BusyBox RootFS
8. Buildroot Product Image
9. Physical Buttons
10. LCD Display
11. C++ Application Core
12. Internet Streaming
13. Multithreaded Streaming Pipeline
14. Physical UI Integration
15. Local Audio Playback
16. Reliability and Automatic Recovery
17. Recovery Boot and eMMC Deployment
18. Final Product Validation

Optional future extensions:

* A/B RootFS update and rollback
* UDP multicast distribution to local network clients
