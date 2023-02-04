# My_Road_to_ROS_Setup

I have started learning ROS (Robotic Operating System) recently. In this repo, I will keep sharing how I setup ROS on my `windows 11`. I found setting up ROS on windows 11 and accessing peripherals such as camera and USB device complicated. The resources available online are confusing and I wasted a lot of time in the last two weeks reading and testing through comments on various forums. I don't want anyone (including me) to go through such pain. 

## Setting up WSL2 and Ubuntu

Now to setup ROS on your `Windows 11`, you will need to setup `WSL2` and `Ubuntu` on your system. You may find instruction for installing [ROS on Windows](http://wiki.ros.org/Installation/Windows) but it will malfunction at several occassions. So, do that on your own risk. Follow [this](https://www.youtube.com/watch?v=wjbbl0TTMeo) tutorial for enabling WSL2 on your PC and downloading Ubuntu. **Remember, you should download `Ubuntu 20.04.5 LTS` version**. Ubuntu versions higher than that are currently not being supported by ROS. 

## Set up ROS

Open your WSL2/Ubuntu terminal and follow the instructions from [here](http://wiki.ros.org/Installation/Ubuntu).

## Installing X Server

Your Ubuntu is a headless OS. So if you want to access anything from Ubuntu that involves GUI, you will need to forward it to a port on your windows system. I tried several techniques to do that, but [this](https://www.youtube.com/watch?v=4SZXbl9KVsw) video worked for me. In addition to that, add the following line to your `~/.bashrc`:

```
export DISPLAY=$(cat /etc/resolv.conf |grep nameserver| sed 's/nameserver //'):0.0
```

## 