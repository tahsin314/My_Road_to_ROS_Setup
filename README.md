# My_Road_to_ROS_Setup

I have started learning ROS (Robotic Operating System) recently. In this repo, I will keep sharing how I setup ROS on my `windows 11`. I found setting up ROS on windows 11 and accessing peripherals such as camera and USB device complicated. The resources available online are confusing and I wasted a lot of time in the last two weeks reading and testing through comments on various forums. I don't want anyone (including me) to go through such pain. 

Now to setup ROS on your `Windows 11`, you will need to setup `WSL2` and `Ubuntu` on your system. You may find instruction for installing [ROS on Windows](http://wiki.ros.org/Installation/Windows) but it will malfunction at several occasions. After that, you will have to setup ROS inside your `Ubuntu` and then configure settings for accessing USB drives etc. 

## Setting up WSL2 and Ubuntu

Follow [this](https://www.youtube.com/watch?v=wjbbl0TTMeo) tutorial for enabling WSL2 on your PC and downloading Ubuntu. **Remember, you should download `Ubuntu 20.04.5 LTS` version**. Ubuntu versions higher than that are currently not being supported by ROS. 