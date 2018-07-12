Based on:
https://learn.adafruit.com/raspberry-pi-video-looper/overview

The files 1_download_dependencies.sh and 2_install.sh are split out from the
original Adafruit instructions.

1_xxx downloads the dependencies.
2_xxx installs the code so that it will start automatically at boot.
Note that if you tweak the code, you will have to re-run 2_xxx in order to
for your changes to take effect. The original Adafruit instructions would
require you to download all of the dependencies and re-install.  So these
two scripts separate those steps so that you do not have to download everything.

video_looper.py is the original Adafruit core video looper code, but enhanced
by providing a GPIO signal interrupt that will skip the currently-playing video
to the next video in the list.  Just replace original video_looper.py with the 
included version.  Then provide a momentary switch between a GPIO pin and ground.
In this code, the switch was placed between GPIO23/(GPIO_GEN4)/16 of the raspi
and a ground pin.

REMEMBER: if you modify the code after you have already installed and gotten it
to run, you'll need to re-run the 2_xxx.sh install script.