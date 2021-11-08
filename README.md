# Autoscrolling-for-linux

A Simple autoscrolling script for linux. The script works systemwide.

## Ubuntu/Ubuntu-based
```
sudo apt-get install xinput
```

## Arch/Manjaro/endeavour
```
sudo pacman -S xorg-xinput
```

## Red Hat/Fedora/CentOS
```
sudo dnf install xinput 
```

After installing the package in your distro, you would need to type the following command:
```
xinput
```

The output should be something like this:
![xinput output](https://raw.githubusercontent.com/Dileep1714/Autoscrolling-for-linux/main/Xinput%20output.jpg)

In my case, my mouse is recognised as Gaming Mouse and its id is 23.
Note: The id of your mouse may change when you disconnect the mouse

Now you will need to type in the following commands:
```
xinput set-prop id "libinput Scroll Method Enabled" 0, 0, 1
```
```
xinput set-prop id "libinput Button Scrolling Button" 2
```

In the above commands, you would need to replace 'id' in the above two commands.
Copy the below script and name it as 'filename.sh'. I named it autoscroller.sh and you can get the file from the repository.
```
#!/bin/bash
xinput set-prop 23 "libinput Scroll Method Enabled" 0, 0, 1
xinput set-prop 23 "libinput Button Scrolling Button" 2
```
Go to properties and mark it as executable or open terminal in the folder and type in:
```
chmod +x filename.sh
```

You can also make a script with these two commands so that they will start with your computer. Check the guides below to run scripts on startup or login in your respective Desktop Environment.


## Gnome/GDM
https://www.simplified.guide/gnome/automatically-run-program-on-startup

## KDE Plasma
https://www.addictivetips.com/ubuntu-linux-tips/autostart-programs-on-kde-plasma-5/
Scroll down to 'Starting up Bash scripts automatically with the GUI' section in the guide

### You can now autoscroll on linux!

