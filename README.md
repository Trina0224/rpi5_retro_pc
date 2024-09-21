# rpi5_retro_pc
Retro PC with current RPI5

The Retro PC module is from: https://www.printables.com/model/694802-retro-desktop-pc-raspberry-pi-case-v2  
Because the base file is not really for the RPI5, I have modified it.  

The pi speaker is not listed in the market. I have to try a different solution.  
My 3.5" screen is this one:  https://osoyoo.com/2024/02/01/how-to-use-hdmi-3-5-with-rpi5/  
The glove of the Audio card is:  https://wiki.keyestudio.com/Ks0314_keyestudio_ReSpeaker_2-Mic_Pi_HAT_V1.0  



The sound card driver is:  https://github.com/HinTak/seeed-voicecard  

Step.1 Hardware ready.  
Step.2 Img the OS into the micro-SD card.  
Step.3 raspi-config --> Advanced Options --> Wayland --> X11  
Step.4 Download the Audio driver and install it.  
Step.5 Put this line into the end of /boot/firmware/config.txt  
  dtoverlay=bw-ads7846,penirq=25,xmin=200,xmax=3900,ymin=200,ymax=3900,speed=50000  
Step.6 follow up with this page to setup the screen: https://osoyoo.com/2024/02/01/how-to-use-hdmi-3-5-with-rpi5/  



also works with: https://www.printables.com/model/718410-retro-tv-raspberry-pi-case-v2  

On my Retro-TV:  
1  ip a 
2  sudo poweroff 
3  sudo apt update 
4  sudo apt upgrade 
5  cd Downloads/ 
6  ls 
7  wget https://github.com/HinTak/seeed-voicecard/archive/refs/heads/v6.6.zip 
8  ls 
9  rm v6.6.zip  
10  wget https://github.com/HinTak/seeed-voicecard/archive/refs/heads/v6.6.zip 
11  uname -a 
12  cat /etc/os-release  
13  sudo raspi-config  
14  sudo nano /boot/firmware/config.txt  
15  cd /boot/overlays
16  sudo wget https://osoyoo.com/driver/HDMI-3.5/bw-ads7846.dtbo
17  sudo reboot
18  clear
19  sudo apt install xserver-xorg-input-evdev
20  sudo apt install -y xinput-calibrator
21  sudo cp -rf /usr/share/X11/xorg.conf.d/10-evdev.conf /usr/share/X11/xorg.conf.d/45-evdev.conf
22  sudo nano /usr/share/X11/xorg.conf.d/99‐calibration.conf
23  sudo reboot
24  sudo nano /usr/share/X11/xorg.conf.d/99‐calibration.conf
25  clear
26  ls
27  cd Downloads/
28  ls
29  unzip v6.6.zip 
30  ls
31  cd seeed-voicecard-6.6/
32  ls
33  sudo ./install.sh 
34  sudo reboot
35  aplay -l
36  history


