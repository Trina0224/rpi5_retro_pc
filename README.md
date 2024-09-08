# rpi5_retro_pc
Retro PC with current RPI5

The Retro PC module is from: https://www.printables.com/model/694802-retro-desktop-pc-raspberry-pi-case-v2  
Because the base file is not really for the RPI5, I have modified it.  

The pi speaker is not listed in the market. I have to try a different solution.  
My 3.5" screen is this one:  
The glove of the Audio card is:  



The sound card driver is:  https://github.com/HinTak/seeed-voicecard  

Step.1 Hardware ready.  
Step.2 Img the OS into the micro-SD card.  
Step.3 raspi-config --> Advanced Options --> Wayland --> X11  
Step.4 Download the Audio driver and install it.  
Step.5 Put this line into the end of /boot/firmware/config.txt  
  dtoverlay=bw-ads7846,penirq=25,xmin=200,xmax=3900,ymin=200,ymax=3900,speed=50000  
Step.6 
