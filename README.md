# My_Road_to_ROS_Setup

I recently started learning ROS (Robotic Operating System), and I am documenting my experience with setting up ROS on my `Windows 11` machine in this repository. The process of setting up ROS and accessing peripheral devices such as cameras and USB devices on Windows 11 has been an utter nightmare. The online resources available are both confusing and unreliable, causing me to waste an unreasonable amount of time over the last two weeks trying to sift through comments on various forums. It is unacceptable that anyone, including myself, should have to endure such a frustrating and time-consuming process.

## Setting up WSL2 and Ubuntu
 
To configure ROS on your Windows 11 machine, it's necessary to set up WSL2 and Ubuntu. While there are [tutorials](http://wiki.ros.org/Installation/Windows) available for installing ROS on Windows, they may not be reliable. Proceed at your own risk. For enabling WSL2 and downloading Ubuntu, refer to [this](https://www.youtube.com/watch?v=wjbbl0TTMeo) tutorial.**Remember, you should download `Ubuntu 20.04.5 LTS` version**. Ubuntu versions higher than that are currently not being supported by ROS. 

## Set up ROS

Open your WSL2/Ubuntu terminal and follow the instructions from [here](http://wiki.ros.org/Installation/Ubuntu).

## Installing X Server

As your Ubuntu setup is headless, GUI access to it requires port forwarding on the host Windows system. After experimenting with various methods, I successfully accomplished this by following [this](https://www.youtube.com/watch?v=4SZXbl9KVsw) video tutorial. To further enhance the setup, add the following line to your `~/.bashrc` file:

```
export DISPLAY=$(cat /etc/resolv.conf |grep nameserver| sed 's/nameserver //'):0.0
```

Run `roscore`, `rqt_graph` in two different terminals and see if they work properly at this stage. If not, go back to any of the earlier steps and try to traceback where it went wrong.

## Set up Camera and other USB Devices (If required)

I encountered numerous difficulties during this phase. After spending significant time troubleshooting, I discovered [this](https://github.com/Katzeee/Notes/blob/master/about-programing/wsl2-using-usb.md) resource to be incredibly useful in resolving my problems. A big shoutout to [@Katzeee](https://github.com/Katzeee) for compiling a top-notch note.

## Initiating ROS for your project

- First, Run `XLaunch` on your windows. Put a check mark on *DISABLE ACCESS CONTROL*

- Open `powershell` as Administrator. Run The following commands:

```
$ usbipd wsl list # Get you the list of usb devices attached to your windows system
$ usbipd wsl attach -b <busid> # Put the busid of your desired device here. For me, when I'm using webcam, it's almost always 2-5
# If an error occurs, execute the following command first
$ usbipd bind --force -b <busid>
``` 

- 
