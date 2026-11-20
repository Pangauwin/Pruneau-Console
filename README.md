# Pruneau-Console

## Introduction

The Pruneau Console is a hardware-software project. The goal is to create a console that can display 3D models, using low level components.

## Status

This project is at its very beginning, no code is written yet, the architecture is being defined, as well as the roadmap. This will soon be updated.

## Hardware

In order to run this project, you will need:
- an ESP32-S3 N16R8: this will have the role of the CPU (+ 8MB PSRAM)
- a Tang Nano 20K: this will have the role of GPU (+ 8MB VRAM)
- some wires/breadboards

These are the bare components you need to run the project. Soon I will add SD card support in order to handle bigger files and data, so you may need a SD card reader. I may include TFT Screen support as well (though HDMI will be the first thing I will be working with).

## Architecture

As mentioned before, the ESP32-S3 will act as a CPU, and the Tang Nano 20K as a GPU. Here is the plan:

### CPU Features

- Handling the main logic of the system
- Transfer data/instructions to the gpu (fixed point)

### GPU Features

- Fixed function pipeline: matrix multiply → triangle setup → rasterizer → z-buffer → framebuffer
- Executing pre-compiled shader instructions (later)
- HDMI Interface

The chips will communicate with each other through SPI (at first, but maybe a 16 bits bus connection with custom protocol will be better if this becomes a bottleneck).

# License

This project is under the [GPL-3.0 License](LICENSE).

Copyright (C) 2026 Pangauwin
