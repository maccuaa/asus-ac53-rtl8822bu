# ASUS USB-AC53 Nano - RTL8822B

Use the following instructions to install the [Edimax EW-7822ULC](https://www.edimax.com/edimax/download/download/data/edimax/global/download/for_home/wireless_adapters/wireless_adapters_ac1200_dual-band/ew-7822ulc) Linux Wifi driver.

This driver adds Linux support for the [ASUS USB AC53 Nano](https://www.asus.com/ca-en/Networking/USB-AC53-Nano/) wireless network adapter.

The following was tested using:

OS: **Fedora 30**

Kernel: **5.1.5-300.fc30.x86_64**

Driver: **EW-7822ULC_Linux_Wi-Fi_Driver_1.0.1.6**

## Instructions

1. Clone this project:

    ```bash
    $ git clone https://github.com/maccuaa/asus-ac53-rtl8822bu.git
    ```

1. Install the kernel-devel package for the kernel you are currently running:

    ```bash
    # Find your current kernel version
    $ uname -r

    $ sudo dnf install kernel-devel-5.1.5-300.fc30.x86_64
    ```

1. Install [ELF Utils](https://sourceware.org/elfutils/):

    ```bash
    $ sudo dnf info elfutils-libelf-devel-0.176-2.fc30.x86_64
    ```

1. Compile the source code:

    ```bash
    make
    ```

1. Install the kernel module:

    ```bash
    sudo make install
    ```

1. Load the kernel module

    ```bash
    sudo modprobe -v 88x2bu
    ```

---

Sources:

- https://wikidevi.com/wiki/ASUS_USB-AC53_Nano

- https://www.edimax.com/edimax/download/download/data/edimax/global/download/for_home/wireless_adapters/wireless_adapters_ac1200_dual-band/ew-7822ulc

- https://github.com/jeremyb31/rtl8822bu