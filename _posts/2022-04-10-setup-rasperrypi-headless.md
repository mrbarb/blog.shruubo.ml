---
title: Setup a Raspberry Pi headless
published: true
---

Hello everyone! This, again, is going to be a fairly quick one, but I just wanted to have a tutorial in case I forget it again, or someone else needs it. For those not aware, the Pi foundation recently removed the default user "pi" in their latest release of Bullseye. They apparently did it to [cause less bruteforce attacks](https://www.raspberrypi.com/news/raspberry-pi-bullseye-update-april-2022/), which defently is a good sign, especially thinking about the large number of not secured pis. So I'll assume you have the latest and greatest version of the Raspberry Pi imager installed, if not, just go [here](https://www.raspberrypi.com/software/). It's really easy to install and overall a great tool.<br>

So, now, having the Raspberry Pi imager installed, we need to choose an OS, and since we're running it headlessly, we can just use Raspberry Pi OS lite. Simply click on choose OS, and Raspberry Pi OS (other).<br>
![rasp_imager](/assets/rasp_imager_home.png) <br>
Then click onto Raspberry Pi OS Lite(32-bit). If you have a Raspberry Pi 4, you could also choose the 64-bit version, but it's a bit less stable as far as I'm concerned.
![choose_os](/assets/choose_rpi_os_lite_32_bit.png) <br>
Now comes the important part, since it has vaguely changed since the last bullseye update, and will lead into simply not working, if not known (at least for me). After choosing your storage device (usually a sdcard), click on the settings icon.
![choose_storage](/assets/choose_storage_sd_card.png) <br>
You will now be presented a variety of options, and you can choose if you'd like to keep them for future flashes, or only use them in this session. It's completely your choice, I just went with "for this session only". You can set up a hostname too, but it's important to choose "Enable SSH".
I always go with password authentication and add the SSH keys later, but you can also do it right away.
![add_user_ssh](/assets/add_user_and_ssh.png) <br>
Also, don't wonder, I blurred the SSH-keys, just in case ;).
The username is completely your choice (pie may not be the best thing to choose :D), but I do recommend a fairly secure password, even if only being used locally, since this also makes brute-force attacks less effective. You can set further things, like WiFi, or locale settings, but I'm pretty sure you can figure them out yourself. One last thing I'd change, is disabling telemetry, but that is up to you.
![disable_tel](/assets/disable_telemetry.png) <br>
Then, simply click "save" and "write". 
Have fun!

Plus: checkout [rpilocator](https://rpilocator.com/) if you need a new pi, but can't find one :D

_If this article helped you, consider [donating](https://blog.shruubo.ml/about)._



###### Sources:
<font size="1">
https://www.raspberrypi.com/news/raspberry-pi-bullseye-update-april-2022/ -news article
</font>