# SaitekX55-joydev

This repository contains a custom kernel driver for the Saitek X55 Rhino HOTAS. It fixes an issue where the throttle and stick are detected as two separate devices, preventing proper configuration in some games and applications.

## Prerequisites

To build and install this driver, you will need the following:

* A Linux system with the appropriate kernel headers installed.

* A build environment, including `make` and `gcc`.

## Installation

Follow these steps to clone, build, and install the driver.

### 1. Clone the Repository

Clone the repository to your local machine using git:

git clone git@github.com:jamespet77/SaitekX55-joydev.git

### 2. Build the Driver

Navigate into the cloned directory and run `make` to compile the driver:

cd SaitekX55-joydev

make

This will create a `joydev.ko` kernel module file.

### 3. Install the New Driver

To install the new driver, you must first remove the currently loaded `joydev` module and then insert the new one.

sudo rmmod joydev

sudo insmod joydev.ko

After these steps, the Saitek X55 should be detected as a single device. You may need to repeat these steps after a system reboot or if the kernel module is reloaded.
