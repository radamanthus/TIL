# Setting up an Nvidia Pascal Graphics card

Remove the graphics card

Install 10.13.2 using UniBeast

Setup MultiBeast and Clover Configurator

Enable TRIM support
```
sudo trimforce enable
```

Use MultiBeast to make ssd bootable

Add the graphics card

Follow the instructions in
https://hackintosher.com/guides/properly-install-nvidia-drivers-high-sierra-10-13/

After setting up the nVidia driver, you will lose network access

Fix network issue: boot from usb installer first to get network access
https://www.tonymacx86.com/threads/solved-ethernet-not-working-after-instaling-multibeast.107931/

Then switch to using the nVidia driver again

---

DO NOT install the 10.13.3 update. You will lose network access again!

---

Fix audio
https://www.tonymacx86.com/threads/creative-sound-core-3d-driver.135298/

1). Download the latest version VoodooChDA
It contains:
* VoodooHDA.kext
VVoodooHDA.prefPane
AppleHDADisabler.kext
VoodooHdaSettingsLoader.app
2). Using Kext Utility installed all Kext's
3). Restart. Now it worked!)
