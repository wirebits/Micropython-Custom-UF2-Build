# Micropython-Custom-UF2-Build
A guide to build custom micropython .uf2 files.

## This guide is for Raspberry Pi Pico Series Microcontroller Boards Only.

# Steps to build custom micropython `.uf2` files
1. Update the Linux System
```
sudo apt update
```
2. Upgrade the Linux System
```
sudo apt full-upgrade -y
```
3. Install Tools
```
sudo apt install git build-essential cmake gcc-arm-none-eabi libnewlib-arm-none-eabi -y
```
4. Download Micropython
```
git clone -b master https://github.com/micropython/micropython.git
```
5. Go to Micropython Folder
```
cd micropython
```
6. Update `pico-sdk` and `tinyusb`
```
git submodule update --init -- lib/pico-sdk lib/tinyusb
```
7. Build `mpy-cross`
```
make -C mpy-cross
```
8. Go to `rp2` Folder
```
cd ports/rp2
```
9. Build `ports/rp2` for RP2040
```
make BOARD=RPI_PICO submodules
```
10. Put your Micropython code in `modules` folder by save the code with file name `main.py`.
11. Exit from `modules` folder.
12. Build your `.uf2` file
```
make
```
- Wait for sometime to complete.
13. Go to `build-RPI_PICO`
```
cd build-RPI_PICO
```
14. There is a file named `firmware.uf2` and this is your code in `.uf2` format.
15. Just copy this in your Raspberry Pi Pico (RP2040) and code will execute automatically.
16. Rename the file with `.uf2` extension to identify and shareable easily.
