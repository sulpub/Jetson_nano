# Jetson_nano
Nvidia Jetson nano development board informations.

# Start with Jetson nano board
## Power the board
For power the board there are two way :
 1. Power with micro usb connector with the power limitation 5V/2A. In this case you can't have a lot of peripheral because 
 with 2A under 5V there are not enough power supply.
 2. Power with Barrel Jack 5V/4A. To use this power supply is **important to connect the jumper J48**.

![Top view board Jetson nano ](https://github.com/sulpub/Jetson_nano/blob/master/images/Jetson_nano_top_board_view.JPG)

# Getting Started With Jetson Nano Developer Kit

There are 4 stages for start using the dev board :
1. Power supply choice (micro usb or jack power). For jack power it's necessary to buy an external power supply (5V/4A)
2. Download the ISO file and install it on an SD card.
3. Setup the first boot with SD card, keyboard, mouse and ethernet connexions.
4. Test Jetson nano environment.

Note : For my board version, the lastest file not work. The correct file is the jetson-nano-sd-r32.1-2019-03-18.zip.

Link ISO jetson nano r32.1-2019-03-18 : (https://nvidia.box.com/shared/static/dp7xma0f4jbvttha6xo14km14fztal7o.zip)

# Enable desktop sharing of embedded UBUNTU

By default there are somes problems to enable desktop sharing.

To activate it, it nesessary to do this
1. Edit the Xml file like : **sudo nano /usr/share/glib-2.0/schemas/org.gnome.Vino.gschema.xml**
2. Add this part on the XML file :
```
<key name='enabled' type='b'>
   <summary>Enable remote access to the desktop</summary>
   <description>
   If true, allows remote access to the desktop via the RFB
   protocol. Users on remote machines may then connect to the
   desktop using a VNC viewer.
   </description>
   <default>false</default>
</key>
```
3. Compile the Gnome schema with : **sudo glib-compile-schemas /usr/share/glib-2.0/schemas**
4. After this, you can enable desktop sharing.

![Jetson enable desktop sharing](https://github.com/sulpub/Jetson_nano/blob/master/images/jetson_nano_desktop_sharing.png)

Source information : http://bit.ly/2onnLIc


# Install jupyter lab

    sudo apt install nodejs npm
    sudo apt install python3-pip
    sudo pip3 install jupyter jupyterlab
    sudo jupyter labextension install @jupyter-widgets/jupyterlab-manager
    jupyter lab --generate-config
