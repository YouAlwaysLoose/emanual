---
layout: archive
lang: en
ref: turtlebot3_opencr_setup
read_time: true
share: true
author_profile: false
permalink: /docs/en/platform/turtlebot3/opencr_setup/
sidebar:
  title: TurtleBot3
  nav: "turtlebot3"
---

<div style="counter-reset: h1 7"></div>

# [OpenCR Setup](#opencr-setup)

![](/assets/images/platform/turtlebot3/software/remote_pc_and_turtlebot.png)

`Note` If you want to get more detail about OpenCR, Please contact an [OpenCR WiKi](/docs/en/parts/controller/opencr10/)
{: .notice--info}


## [OpenCR1.0 Firmware Upload for TB3](#opencr10-firmware-upload-for-tb3)

`Note` You can choose one of methods for uploading firmware. But we highly recommend to use **shell script**.
{: .notice--info}

### [Shell Script](shell-script)
  
`Note` This instruction was tested on `Ubuntu 16.04`, `Ubuntu Mate`, `Linux Mint` or `Raspbian` and OpenCR1.0 software setup can be done from `Intel® Joule™`, `Raspberry Pi 3`.
{: .notice--info}

  - TurtleBot3 Burger

``` bash
$ export OPENCR_PORT=/dev/ttyACM0
$ export OPENCR_MODEL=burger
$ rm -rf ./opencr_update.tar.bz2
$ wget https://github.com/ROBOTIS-GIT/OpenCR/raw/develop/arduino/opencr_release/shell_update/opencr_update.tar.bz2 && tar -xvf opencr_update.tar.bz2 && cd ./opencr_update && ./update.sh $OPENCR_PORT $OPENCR_MODEL.opencr && cd ..
```

![](/assets/images/platform/turtlebot3/opencr/shell01.png)

When firmware upload is completed, `jump_to_fw` text string will be printed on the terminal.

  - TurtleBot3 Waffle or Waffle Pi

``` bash
$ export OPENCR_PORT=/dev/ttyACM0
$ export OPENCR_MODEL=waffle
$ rm -rf ./opencr_update.tar.bz2
$ wget https://github.com/ROBOTIS-GIT/OpenCR/raw/develop/arduino/opencr_release/shell_update/opencr_update.tar.bz2 && tar -xvf opencr_update.tar.bz2 && cd ./opencr_update && ./update.sh $OPENCR_PORT $OPENCR_MODEL.opencr && cd ..
```

![](/assets/images/platform/turtlebot3/opencr/shell02.png)

When firmware upload is completed, `jump_to_fw` text string will be printed on the terminal.

### [Arduino IDE](#arduino-ide)

`Warning` The contents in this chapter corresponds to the `Remote PC` (your desktop or laptop PC) which will control TurtleBot3. Do **NOT** apply this instruction to your TurtleBot3.
{: .notice--warning}

Before you following step, please setup Arduino IDE

  - [Arduino IDE for using OpenCR](/docs/en/parts/controller/opencr10/#arduino-ide)

OpenCR1.0 firmware (or the source) for TB3 is to control DYNAMIXEL and sensors in the ROS. The firmware is located in OpenCR example which is downloaded by the board manager.
If you have TurtleBot3 Burger,

**[Remote PC]** Go to `File` → `Examples` → `turtlebot3` → `turtlebot3_burger` → `turtlebot3_core`.

If you have TurtleBot3 Waffle or Waffle Pi,

**[Remote PC]** Go to `File` → `Examples` → `turtlebot3` → `turtlebot3_waffle` → `turtlebot3_core`.

![](/assets/images/platform/turtlebot3/opencr/o1.png)

**[Remote PC]** Click `Upload` button to upload the firmware to OpenCR1.0.

![](/assets/images/platform/turtlebot3/opencr/o2.png)

![](/assets/images/platform/turtlebot3/opencr/o3.png)

`Note` If error occurs while uploading firmware, go to `Tools` → `Port` and check if correct port is selected. Press `Reset` button on the OpenCR1.0 and try to upload the firmware again.
{: .notice--info}
  
**[Remote PC]** When firmware upload is completed, `jump_to_fw` text string will be printed on the screen.
