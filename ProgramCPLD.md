
 ## RaspberryPi Setup for programming the CPLD: 
Install Rasbian OS with the Raspberry Pi Imager, setup SSH, setup WiFi, setup the user einrichten e.g. 

- **User: pi**

with
- **Password: raspberry**
- Connect with putty or Windows Powershell
    
    
    ```
    ssh PiUser@IP-Address
    ```
    
    e.g.:
    
    ```
    ssh mancloud@192.168.0.15
    ```
    
    send the following commands to the pi:
    
    ```
    sudo apt update
    sudo apt -y dist-upgrade
    sudo apt install build-essential libusb-dev libftdi-dev libgpiod-dev git cmake
    git clone https://github.com/matrix-io/xc3sprog
    mkdir xc3sprog/build
    cd xc3sprog/build
    cmake .. -DUSE_WIRINGPI=OFF
    make
    sudo make install
    ```
    
    now you need to copy the .jed file onto the Raspberry over ssh. With the Windows Powershell it would be:
    
    ```
    scp ./gc_ipl.jed mancloud@192.168.0.15:xc3sprog/build
    ```
    
    now the file is in the same directory as the xc3sprog. The file could be anywhere on the pi's filesystem but it makes it easier and then you have to edit the path for the file in the following command. 

The **KunaiGC** uses the SOICbite-Interface to program the CPLD and Flash. You need an SOIC-8 Test Clip and modify it a little bit.
Actually Mi213 has an awesome [tutorial](https://github.com/Micha213/BlueRetro-PS1-2-Receiver/wiki/Flash-PCB#soicbite)  how to prepare the SOIC-8 Test Clip for this usecase. Thanks to Mi213 to let use refer to it :)

Now connect the SOICbite between the RaspberryPi and the **KunaiGC** 

![](https://github.com/KunaiGC/KunaiGC/blob/e74e694fb9b1ebc6c7877027f4c3de27b43bf00e/images/Diagram_cpld.jpg)
![](https://github.com/KunaiGC/KunaiGC/blob/80a42bc84a418dbd0005471d2135046b508b41be/images/soicbite-pinout.jpg)
![](https://github.com/KunaiGC/KunaiGC/blob/a6744ee455d6b89b1c49a5aaf6fcaeeba9615400/images/raspi_soicbite.jpg)


and send the following command with the Powershell:
    
    ```
    sudo xc3sprog -c sysfsgpio_creator -j
    ```
    
    if everything is soldered and connected correctly the output should be like this:
    
    ```
    JTAG loc.:   0  IDCODE: 0x59604093  Desc:                       XC9536XL Rev: E  IR length:  8
    ```
    
    now you know, that the CPLD is recognized correctly - we keep an eye on the  _**JTAG loc.:**_ which is  _**0**_ in this case and then we send the flash command to flash the .jed-file onto the CPLD
    
    ```
    sudo xc3sprog -c sysfsgpio_creator -v -p 0 ~/xc3sprog/build/gc_ipl.jed
    ```
    
    the CPLD will now be programmed and and verified at the end. If this is successful:
    
    ```
    Success! Verify time xxxx.x ms
    ```
Now you need to solder and test it :)