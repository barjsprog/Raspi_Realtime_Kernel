# Raspi_Realtime_Kernel
Raspberry Pi 3B Realtime Kernel Ready. 

After setting up Raspberry Pi Raspbian OS.

Put the file in to the raspberry pi /tmp folder. 

After adding the file,

```
  ~$ cd /tmp
  /tmp$ tar xzf rt-kernel.tgz
  /tmp$ cd boot
  /tmp/boot$ sudo cp -rd * /boot/
  /tmp/boot$ cd ../lib
  /tmp/lib$ sudo cp -dr * /lib/
  /tmp/lib$ cd ../overlays
  /tmp/overlays$ sudo cp -d * /boot/overlays
  /tmp/overlays$ cd ..
  /tmp$ sudo cp -d bcm* /boot/
```

Add the following entry to /boot/config.txt:
```
  ~$ sudo nano /boot/config.txt
  # Add the following option:
  kernel=vmlinuz-4.14.91-rt49-v7+
```

Reboot the Raspi.

To check: 
```
  ~$ uname -r
  4.14.91-rt49-v7+
```
Source: https://lemariva.com/blog/2018/07/raspberry-pi-preempt-rt-patching-tutorial-for-kernel-4-14-y

