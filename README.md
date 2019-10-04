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
    sudo jupyter labextension install @jupyterlab/statusbar
    jupyter lab --generate-config
    sudo jupyter --build
    jupyter notebook password   

Source : https://github.com/NVIDIA-AI-IOT/jetbot/wiki/Create-SD-Card-Image-From-Scratch

# Run jupyter lab

    jupyter notebook --ip=0.0.0.0   //for running jupyter
    link to start on Jetson Nano : http://192.168.55.1:8888/lab? or http://127.0.0.1:8888/lab?
    
# Tensorflow on Jetson nano
Nvidia official TensorFlow release for Jetson Nano! (Python3.6+JetPack4.2.1)

    $ sudo apt-get install libhdf5-serial-dev hdf5-tools libhdf5-dev zlib1g-dev zip libjpeg8-dev
    $ sudo apt-get install python3-pip
    $ sudo pip3 install -U pip
    $ sudo pip3 install -U numpy grpcio absl-py py-cpuinfo psutil portpicker six mock requests gast h5py astor termcolor protobuf keras-applications keras-preprocessing wrapt google-pasta
    $ sudo pip3 install --pre --extra-index-url https://developer.download.nvidia.com/compute/redist/jp/v42 tensorflow-gpu==1.14.0+nv19.7

DL frameworks - https://developer.nvidia.com/deep-learning-frameworks

Download - https://developer.qa.nvidia.com/embedded/downloads#?search=tensorflow

Installation guide - https://docs.nvidia.com/deeplearning/frameworks/install-tf-jetson-platform/index.html

Release note - https://docs.nvidia.com/deeplearning/dgx/install-tf-xavier-release-notes/index.html

## JetCard

JetCard is a system configuration that makes it easy to get started with AI. It comes pre-loaded with

    A Jupyter Lab server that starts on boot for easy web programming

    A script to display the Jetson's IP address (and other stats)

    The popular deep learning frameworks PyTorch and TensorFlow

After configuring your system using JetCard, you can get started prototyping AI projects from your web browser in Python.

See also

    **JetBot** - An educational AI robot based on NVIDIA Jetson Nano

    **JetRacer** - An educational AI racecar using NVIDIA Jetson Nano

    **JetCam** - An easy to use Python camera interface for NVIDIA Jetson

    **torch2trt** - An easy to use PyTorch to TensorRT converter

